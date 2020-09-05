# Orientação a Objetos - OOP

## Pilares fundamentais
É essencial possuir um claro conhecimento dos princípios da orientação á objetos para poder aplicar as melhores práticas de design de código, padrões e abordagens de arquitetura

* Estado
* Comportamento
* Abstração
* Herança
* Polimorfismo
* Encapsulamento

Na orientação á objetos devemos sempre buscar o baixo acoplamento e a alta coesão entre os objetos

### Acoplamento
Uma dependência direta entre um objeto e outro. Quando um objeto muda, o outro muda por consequência

### Coesão
Objetos executando uma única responsabilidade, livres de um dependência direta com um outro objeto

## Estado e Comportamento
Ambos estão atrelados à classe
### Estado
Quando uma propriedade possui um valor definido. São informações que vão estar no objeto.
```
class Person {
  public name = 'Jorge'
  public age = '28'
}
```

### Comportamento
Quando um método possui uma ação ou modifica o estado da entidade
```
class Person {
  public changeName(newName) {
  this.name = newName
  }
}
```

### Classe
Estrutura de código que tem a função de mapear um objeto do mundo real para uma estrutura de informação em código.

### Objeto
Quando a classe é instanciada, ou seja, passa a estar na memória como um objeto.

## Herança
Quando uma classe específica "herda" as propriedades (estados) e métodos (comportamentos) de uma classe mãe.
```
class Employee extends Person {

}
```
**Dica**: Na hora de modelar os objetos/classes fazer a pergunta: "{classe} é um(a) {classe mae}?" se a resposta não fizer sentido a herança não está correta. Exemplos:
* Correto: "Funcionário é uma Pessoa?" SIM :)
* Errado:  "Funcionário é um Livro?" Não :(

## Abstração
A ideia por trás da abstração é oferecer um conjunto de comportamentos que abstraia uma certa especialização.

## Polimorfismo
Ter muitos comportamentos para uma mesma coisa

## Encapsulamento
É o ato de "esconder" certos comportamentos que são privados, nesse caso expomos um método publico que implementa os métodos privados.

## Interface x Implementação
### Interface
É uma espécie de contrato, portanto, toda classe que implementa um interface é obrigada a implementar os métodos que estão especificados na interface

## Herança x Composição
### Herança
Toda herança precisa ser justificada e serve para abstrair comportamentos comuns que podem ser derivados pelas classes filhas.
