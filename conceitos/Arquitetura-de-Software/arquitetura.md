# Arquitetura

## Estilo arquitetural
É uma abordagem de como projetar e entregar uma aplicação
Trata-se de como organizar os componentes responsáveis de uma arquitetura, como eles irão interagir entre si e quais aspectos tecnológicos irão atender

### Arquitetura Monolítica

### Arquitetura em Camadas

### Arquitetura REST

### Arquitetura de Micro-services

## Padrões Arquiteturais
* São semelhantes aos Design Patterns, só que o escopo é diferente
* São estratégias de alto nível que dizem respeito a componentes de grande escala, as propriedades de mecanismos globais de um sistema
* Um projeto de arquitetura pode conter diversos estilos arquiteturais e cada estilo arquitetural pode usar diversos padrões arquiteturais. Um padrão arquitetural pode ser um subconjunto de um estilo arquitetural visando um escopo específico
* O padrão arquitetural é uma solução geral e reutilizável para um problema em um contexto particular. É uma solução recorrente para um problema recorrente.


### 3-Tier Architecture (Arquitetura 3 Camadas)
* Clássica maneria de distribuir responsabilidades:
  * Apresentação
  * Aplicação (negócios)
  * Acesso à dados
* Não deve ser menosprezada, pois nem sempre a complexidade é uma solução para problemas simples
* Pode ser aplicada em diversos cenários, porém geralmente é mais encontrada em aplicações com foco comercial (cadastros, regras etc)

### Onion Architecture (Clean architecture)

### Hexagonal Architecture "Ports & Adapters"
* Aplicar os conceitos de Onion, DDD, Clean architecture, CQRS tudo junto

### CQRS - Command Query Responsibility Segregation
* É um padrão arquitetural onde o foco é separar os meios de leitura e escrita de dados. Alterações de dados são realizados via **Commands** e leituras de dados são realizados via **Queries**
* O objetivo é prover expressividade para a aplicação, pois todos os commands representam uma intenção de negócio
* Promove a consistência eventual, que é quando possuímos um banco de leitura e outro de escrita com os mesmos dados, porém os dados não são consistidos exatamente no mesmo momento
* Muito aplicado em arquiteturas hexagonais, micro-serviços ou em aplicações que possuem uma alta demanda de consumo de dados

#### **Commands**
Representam uma intenção de mudança no estado de uma entidade. São expressivos e representam uma única intenção de negócio ex: *AumentarSalarioFuncionarioCommand*

#### **Queries**
É a forma de obter dados de um banco ou origem de dados para atender as necessidades da aplicação

### Event Sourcing
* Podemos buscar o estado de uma aplicação para encontrarmos o estado atual do mundo e isso responde muitas perguntas. Entretanto há momentos em que nós não só queremos ver onde estamos mas também como chegamos lá.
* Event Sourcing assegura que todas as mudanças feitas no estado de um aplicação são armazenadas como uma sequencia de eventos. Não só podemos buscar estes eventos, mas também podemos usar estes logs de eventos para reconstruir estados passados e ajustar automaticamente o estado atual com mudanças retroativas.
* A ideia central é persistir todos os estados anteriores de uma entidade de negócio desde o momento de sua criação. Com estes dados é possível realizar o replay dos fatos passados para entender o comportamento do usuário, trabalhar com Big Data, Machine Learning, realizar testes de integração com cenários reais ou simplesmente recriar as entidades se necessário.

## DDD - Domain-Driven Design
* Indicado para aplicações complexas com muitas entidades e regras de negócio
* Razoavelmente fácil de entender e difícil de aplicar
* Um guia de como entender um negócio, organizá-lo em um conjunto de princípio, criar uma modelagem com base no negócio e implementar utilizando diversas boas práticas

#### **Processo de implementação do DDD**
* Entender o negócio
* Extrair a linguagem ubíqua
  * Vocabulário de todos os temos do domínio
  * Compartilhada por todas as partes envolvidas no projeto
  * É utilizada em todas s formas faladas e escritas de comunicação
* Trabalhar a modelagem estratégica
  * Extrair a linguagem ubíqua vai colaborar na visão e entendimento do negócio e como segregar seu domínio em partes menores e responsáveis
  * Para documentar estas segregações responsáveis utilizamos o *Mapa de contextos* que pode ser representado através de imagens e uma simples documentação do tipo de relacionamento entre os contextos
  * Cada contexto delimitado possui sua própria linguagem ubíqua, pois em contextos diferentes, os temos podem ter significados diferentes
* Definir arquitetura
* Desenvolver a modelagem tática
  * Aggregate Object
  * Uma entidade que é a raíz agregadora de um processo do domínio que envolve mais de uma entidade
  * Domain Model
  * Uma entidade do domínio, possui estados e comportamentos, lógica de negócio, getters e setters, adHoc etc
  * Value Object
  * Um objeto que agrega valor às entidades, não possui identidade e é imutável
  * Factory
  * Classe responsável por construir adequadamente um objeto / entidade
  * Domain Service
  * Serviço do domínio que atende partes do negócio que não se encaixam em entidades específicas
  * Trabalha com diversas entidades
  * Realiza persistência através de repositório
  * Application Service
  * Serviços de aplicação que orquestra ações disparadas pela camada de apresentação e fornece DTOs para comunicação entre as demais camadas e para o consumo da camada de apresentação
  * Repository
  * Uma classe que realiza a persistência das entidades se comunicando diretamente com o meio de acesso aos dados
  * É utilizado apenas um repositório por agregação

## Arquiteturas Evolutivas
* Um arquiteto permite que decisões importantes sejam adiadas e um bom arquiteto maximiza o número de decisões não tomadas
* Uma arquitetura evolutiva suporta mudanças continuas e incrementais como um primeiro princípio por meio de vários aspectos
* Mudanças são inevitáveis. A evolução no entanto, é opcional

### Sempre considere a complexidade!
#### **Acidental**:
É aquela que surge durante o processo de desenvolvimento, ou seja, ela é **CAUSADA** pela abordagem escolhida para resolver o problema.

#### **Essencial**
Já é essencial, é basicamente a complexidade que nosso software se propõe a resolver.
SIM! Infelizmente existem problemas complexos e é neles que devemos focar.

## Conway's Law
> Qualquer empresa que projeta um sistema, inevitavelmente produz um projeto cuja estrutura é uma cópia da estrutura de comunicação da organização. *Meivin Conway*

## Agilidade e o Manifesto Ágil
* **Indivíduos e interações** mais que processos e ferramentas
* **Software em funcionamento** mais que documentação abrangentes
* **Colaboração com o cliente** mais que negociação de contratos
* **Responder à mudanças** mais que seguir um plano

### Manifesto Ágil
* Nossa maior prioridade é satisfazer o cliente, através da entrega adiantada e contínua de software de valor
* Aceitar mudanças de requisitos, mesmo no fim do desenvolvimento. Processos ágeis se adequam à mudanças, para que o cliente possa tirar vantagens competitivas
* Entregar software funcionando com frequência, na escala de semanas até meses, com preferência aos períodos mais curtos
* Pessoas relacionadas à negócios e desenvolvedores devem trabalhar em conjunto e diariamente durante todo o curso do projeto
* Construir projetos ao redor de indivíduos motivados, dando à eles o ambiente e suporte necessário e confiar que farão seu trabalho
* O método mais eficiente e eficaz de transmitir informações para, e por dentro de um time de desenvolvimento, é através de uma conversa cara a cara
* Software funcional é a medida primária de progresso
* Processos ágeis promovem um ambiente sustentável. Os patrocinadores, desenvolvedores e usuários devem ser capazes de manter, indefinidamente, passos constantes
* Contínua atenção à excelência técnica e bom design aumenta a agilidade
* Simplicidade: a arte de maximizar a quantidade de trabalho que não precisou ser feito
* As melhores arquiteturas, requisitos e designs emergem de times auto-organizáveis
* Em intervalos regulares, o time reflete como fica mais efetivo, então, se ajustam e otimizam seu comportamento de acordo

## DevOps
* O termo "DevOps" deriva das palavras "Desenvolvimento" e "Operações" sendo uma prática de engenharia de software que possui o intuito de unificar o desenvolvimento de software (Dev) e a operação de software (Ops)
* A característica principal do movimento DevOps é defender fortemente a automação e monitoramento em todas as fases da construção do software, da integração, teste, liberação para implantação e gerenciamento de infrastructure
* Pretende fornecer, em ciclos de desenvolvimento menores:
  * Frequência de implantação aumentada
  * Liberações mais seguras, em alinhamento próximo com os objetivos de negócio

## Principios DRY, KISS e YAGNI
### DRY (Dont Repeat Yourself)
Cada parte do conhecimento deve ter uma representação, não ambígua e definitiva dentro da aplicação

### KISS (Keep It Simple, Stupid)
O KISS valoriza a simplicidade do projeto e defende que toda a complexidade desnecessária seja descartada

### YAGNI (You ain't gonna need it)
Uma orientação que sugere não adicionar funcionalidades ao código fonte de uma aplicação até que essas sejam realmente necessárias
