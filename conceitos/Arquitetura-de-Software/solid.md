# SOLID
É um acrônimo dos 5 primeiros princípios da programação orientada a objetos e design de códigos identificado por Robert C Martin (ou Uncle Bob) por volta dos anos 2000

Os princípios de SOLID precisam ser aplicados para se obter os benefícios da orientação à objetos tais como:
* Seja fácil de se manter, adaptar e se ajustar às alterações de escopo
* Seja testável e de fácil entendimento
* Seja extensível para alterações com o menor esforço necessário
* Que forneça o máximo de reaproveitamento
* Que permaneça o máximo de tempo possível em utilização

Problemas muito comuns que podemos evitar utilizando os princípios do SOLID
* Dificuldade na testabilidade / criação de testes unitários
* Código macarrônico sem estrutura ou padrão
* Dificuldades de isolar funcionalidades
* Duplicação de código, uma alteração precisa ser feita em N pontos
* Fragilidade, o código quebra facilmente em vários pontos após alguma mudança

## SRP - Single Responsibility Principle
Uma classe deve ter um, e apenas um, motivo para ser modificada, ou seja, faz apenas uma coisa.

## OCP – Open Closed Principle
Entidades de software (classes, módulos, funções etc) devem estar abertas para extensão, mas fechadas para modificação.

## LSP- Liskov Substitution Principle
Se q(x) é uma propriedade demonstrável dos objetos x de tipo T.
Então q(y) deve ser verdadeiro para objetos y de tipo S onde S é um subtipo de T.

Subclasses devem ser substitutíveis por suas Superclasses

O principal objetivo do LSP é questionar se o desenvolvedor está realizando uma herança dentro dos padrões de design e abstração ou está apenas seguindo a linha do "é um.."

## ISP - Interface Segregation Principle
Clientes da interface (classe) não devem ser forçados a depender de métodos que não usam
Muitas interfaces especificas são melhores do que uma interface única.

Programe voltado à interface, não à implementação.

## DIP - Dependency Inversion Principle
Módulos de alto nível não deveriam depender de módulos de baixo nível. Ambos devem depender de abstrações. Abstrações não devem depender de detalhes, detalhes devem depender de abstrações.

Dependa de uma abstração (interface) e não de uma implementação (classe concreta).
