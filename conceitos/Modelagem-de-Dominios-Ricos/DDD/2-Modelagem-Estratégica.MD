# Modelagem Estratégica

## Context Map

## Bounded Context
* "Contexto delimitado" onde um elemento tem um significado bem definido
  * Todos os elementos da linguagem ubíqua
* Além dos limites do contexto, a linguagem muda
  * Cada contexto delimitado tem sua própria linguagem ubíqua
* Domínio dividido em uma teia de contextos interconectados
  * Cada contexto delimitado tem sua arquitetura e implementação
* Interface de serviços
  * Para integração com serviços externos

### Motivação para usar Bounded Context
  * Remover ambiguidade e duplicação de código
  * Simplificar o design dos módulos
  * Integração dos componentes externos

### Domínio e contextos
* Todos os contextos forma o Domínio
![](https://thedomaindrivendesign.io/wp-content/uploads/2019/06/DomainDrivenDesignReference.png)

## Definindo contextos delimitados
Como já vimos, cada contexto delimitado consiste em ter
* Sua própria linguagem ubíqua
* Sua própria arquitetura, a escolha vai depender da complexidade e solução
* Interfaces de serviços, para integração com outros serviços

## Modelo de Negócio vs Modelo de Domínio
* Quebrar o modelo de negócio indo pro modelo de dominio evita a "Grande bola de lama"

## Integridade do Modelo
### Sinais de qu o modelo está em risco
* O mesmo termo tem significados diferentes para times diferentes
* O mesmo termo representa elementos diferentes
* Dependência com sistemas externos
* Dependência com código legado
* Áreas funcionais da aplicação são melhor tratadas separadamente

### Visão dos contextos delimitados
* A aplicação é resultado de uma composição de múltiplos contextos
  * EX: Loja virtual, vendas, fiscal, logística
* O número de contextos delimitados reflete  a organização física da empresa
  * Um contexto delimitado para cada departamento da empresa

## Tipos de relacionamento entre contextos
* Contextos **Upstream** influenciam contextos **Downstream**

### Conformist
* Contextos Downstream dependem de contextos Upstream
* Nenhuma negociação é permitida

### Customer / Supplier
* Contextos Customer dependem de contextos Supplier
* Oportunidade de levantar preocupações e abordar alguma solução

### Partners
* Dependência mutua entre dois contextos

### Shared Kernel
* Um modelo compartilhado não pode ser alterado sem consultar os times que dependem dele

### Anti-Corruption Layer
* Camada adicional dando ao contexto Downstream uma interface fixa independente do que acontece com o contexto Upstream
