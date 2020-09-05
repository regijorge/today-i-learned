# Modelagem Tática

## Domain Module
### Abordagem clássica do DDD
#### Camadas de Domínio
* Domain Models
  * Aggregates
  * Entities
  * Value Types
  * Factories
* Domain Services
  * Cross-aggregate behavior
  * Repositories
  * External Services

### Clareando os equívocos
* Modelos de Domínio
  * Mapear o contexto é fundamental
  * Modelar os objetos de domínio conforme identificados na Linguagem ubiqua
* Database Agnostic
  * O modelo deve ser fácil de persistir
  * Persistir não deve ser a sua única preocupação
  * A principal preocupação deve ser manter o sentido com o processo de negócio do domínio
* Ubiquitous Language
  * Entender da linguagem para entender do negócio
  * Manter a linguagem do negócio alinhada ao negócio

### Camadas de Domínio
* Domain Model
  * Modules
  * Entities
  * Values
* Domain Services
  * Repositories
  * Proxies

### O que seria um domain module?
Conjunto de:
* Aggregates (agregações)
* Entities (entidades)
* Value Objects (objetos de valor)

## Objetos de Valor
* Coleção de dados individuais
* Agrega valor à alguma coisa, à uma entidade por exemplo
* Não é persistido individualmente no banco
* Destinado para ser uma coleção de atributos
* Imutável
* Mais preciso que os tipos primitivos
* Pode ser representado por uma classe com métodos
```
// Tipo primitivo
const cpf = '123456768910'

// Objetos de valor
const cpf = {
  number: '123456768910',
  name: 'Nome da pessoa fisica'
  expedition: '1990-10-01'
}
```

## Entidades
* Possuem identidade
* Deve ser exclusiva para o objeto mapeado
* Possui estados e comportamentos
* Possui lógica de negócios mas não faz persistência
* É mutável

## Agregações
* Um conjunto de entidades usadas e referenciadas juntas
* Um conjunto de entidades tratadas como uma só quando o dado é alterado
* Possui uma raíz de agregação (Aggregate Root)
* A agregação (Aggregate Root) mantém a integridade das classes filhas

### O que é comportamento?
* Métodos que validam o estado do objeto (entidade)
* Métodos que invocam regras de negócio e alteram o estado do objeto
* Métodos que expressam o processo do negócio envolvendo o objeto

### Fatores de uma agregação
* Limitar o acesso aos objetos filhos
* Certificar que o estado dos objetos filhos está sempre consistente
* Os limites reais de uma agregação é determinada pela regra de negócio

### Responsabilidades da agregação
* Certificar sempre a consistência do estado dos objetos filhos
* Cuidar da integridade de todos os objetos filhos
* Intermediar a adição / edição / exclusão dos objetos filhos
* Acesso aos objetos filhos deve ser sempre por ações
* Utilize um único repositório por agregação


## Serviços de Domínio
* Implementam lógicas de negócio que não pertencem a um agregado em particular e trabalham com múltiplas entidades
* Coordenam a atividade dos agregados e repositórios com o propósito de implementar a ação de negócio
* Podem consumir serviços da infraestrutura como enviar emails, eventos ou mensagens
* As ações realizadas pelos serviços de domínio estão previstas por requisitos e são permitidas e aprovadas pelos Domain Experts

### Exemplo de serviço de domínio
#### Determinar se um cliente atingiu o status "platinum"
* O cliente para ser "platinum" precisa ter atingido mais de R$ 5.000,00 em compras
  * Necessidade de consultar pedidos e produtos para determinar a somatória
  * Não é responsabilidade da agregação acessar esses dados, pois seu papel é processar e não persistir
  * Valores são definidos nas novas instâncias das entidades
  * Se trata de uma regra de negócio "cross-aggregate"
  * Restrito ao processo de negócios

#### Alugando uma sala de reunião
* Alugar uma sala requer validar a disponibilidade da sala e processar o pagamento
  * Reserva (domain service)
  * Valida a disponibilidade da sala
  * Realiza a transação com o mecanismo
  * Reserva (agregação)
  * Sala e projetos filhos
  * O repositório da agregação realiza a ação

## Repositório
* No Domain Model, o repositório é apenas uma classe que persiste as entidades e agregações
* É o tipo de classe mais popular do serviço de domínio
* Cuida de persistir os agregados
* Apenas um repositório por agregação
* Possui dependência direta com o meio de acesso a dados
* Um repositório é onde vocẽ pode tratar com comandos SQL e connection string

### Não existe uma forma errada de fazer um repositório
* Pode ser genérico
* Pode ser especializado
* Pode conectar diretamente no banco e trabalhar com ADO
* Pode utilizar um ORM
* Pode consultar serviços externos
* Deve retornar e persistir dados, fazer isto bem feito e somente fazẽ-lo


## Eventos de Domínio
* Apesar de não serem obrigatórios eles podem oferecer uma resiliência efetiva para expressar comportamentos do mundo real
* Disparar um evento para concluir determinada tarefa baseada em ações que vão além da responsabilidade do domínio. Ex: enviar um email pro cliente após a conclusão do processo de compra

### Benefícios
* Disparar um evento de domínio para ações relevantes
* Não é necessário ter todo o código em um único lugar
* Disparar um evento sem necessidade de conhecer o que ele faz
* Manipular o mesmo evento em lugares diferentes
