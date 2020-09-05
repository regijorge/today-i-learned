# Estilos e Padrões Arquiteturais

## Modelo clássico de 3 camadas
* Presentation
* Business
* Data

## Definindo um estilo arquitetural
### Entendimento do negócio
#### UX
A aplicação é uma API ou usa Interface de Usuário (telas)?

#### Use-Cases / Presentation
Definir Casos de Uso)

#### Business / Application
Definir negócio com base na história de usuário e casos de uso que precisa implementar

#### Persistência / Data
* Persistência Hibrida
  * Relacional
  * NoSQL
  * Memória / Cache

#### Padrões
A escolha do padrão vai depender da análises dos itens citados acima
* Transaction Script
* Table Module
* Domain Model
* CQRS
* Event Sourcing


## Transaction Script Pattern
### Ações da aplicação
* Cada processo engloba uma única ação
* A ideia é criar processos (métodos) que resolvam uma única responsabilidade

### Transação lógica
* Apresentação e dados

### Ações comuns
* São divididas em processos delimitados para reuso
* Módulos possuem todos os métodos que processam os dados

## Table Module Pattern
### Banco de Dados
* 1 Módulo por tabela no banco de dados
* Módulos possuem todos os métodos que processam os dados
  * get, save, create, update, delete....
  * Requer queries e comandos
* Limitação de módulos para tabelas significantes
  * Tabelas com chaves estrangeiras para relacionamento


## Domain Model Pattern
### Aggregate Objects (Entidade)
* Dados e comportamento

### Persistência Agnóstica
* Vocẽ tem um repositório que não "sabe" se está usando um ORM ou qualquer do tipo, apenas sabe que está salvando um dado

### Alinhada com os serviços de Domínio


## Arquitetura Cebola - Clean Architecture
* Clean Architecture


## Arquitetura Hexagonal (Ports and Adapters)
![](https://miro.medium.com/max/2200/0*Ik1SZ997_fZ-vi8o.)


## Camadas sugeridas para atender o Domain Model
### Camada de apresentação
* Liga o usuário ao resto da aplicação
* Pode ser um MVC, Web API, REST, Mobile, SPA...
* Está duplamente ligada à camada de aplicação (Input e Output)

#### Entregar aplicações modernas é crítico
* É necessário prover uma interface rica para executar todas as operações
  * É necessário trabalhar com diversos componentes e frameworks
* Vocẽ tem a responsabilidade de prover uma experiẽncia de uso rica
  * Chamadas assíncronas
  * Retorno silencioso
  * Facilidade de encontrar a informação

#### Aspectos da camada de apresentação
* Baseada em ações descritas nos casos de uso
* Responsiva (Device friendly)
* User friendly
* Compatível com o processo na vida real (ex: carrinho de compra)

### Camada de aplicação
* Envia a informação para a camada de apresentação
* Orquestra ações disparadas por elementos da Aplicação
* Duplamente ligada com a camada de apresentação (Input e Output)

#### Definição das camadas de negócio
* Aplicação
  * Dependente dos casos de uso
  * Entidades de aplicação
  * Processos da aplicação
  * DTO (Data Transfer Object)
  * Applicaton Services
* Domínio
  * Não depende dos casos de uso
  * Entidades de negócio
  * Processos de negócio
  * Domain Model
  * Domain Service

### Camada de Domínio
#### Modelos do domínio
* Pode ser entidade baseada em OOP (Orientação à Objetos)
* Pode ser um modelo funcional

#### Guia para as classes (entidades)
* Convenções do DDD (factories, value types, private setters)
* Dados e comportamento

#### Modelo anêmico
* Apenas propriedades (dados do modelo)
* Comportamentos e regras implementadas no serviço

### Serviços de Domínio
* Partes do domínio que não se encaixam em entidades existentes
  * Classes que agrupam comportamentos diversos
  * Tipicamente trabalhando com diversas entidades
  * Implementação de processos que:
  * Requerem acesso à persistência para ler e gravar
  * Requerem acesso à serviços externos

## Camada de Infraestrutura
* Persistência
* Segurança
* Logging e Tracing
* INversão de controle
* Cache
* Network
* ...

### Isole os detalhes da camada de infra
* Deixe os detalhes de forma separada (evite hardcoded)
* Connection string
* Senhas, usuário
* Em alguns casos faça uso de facade
