# Clean Code

## O que é um código limpo
* Simples! Não precisa fazer nad além do que tem que fazer e da forma mais simples possível
* Direto ao ponto
* Eficiente
* Sem duplicidade
* Elegante
* Feito com cuidado
* Fácil de ler

> Qualquer tolo consegue escrever código que um computador entenda. Bons programadores escrevem códigos que humanos conseguem entender. *Martin Fowler*

## Como medir um bom código?
* Linhas de código
* Número de métodos
* Número de classes
* Linhas de código por método
* Complexidade ciclomática (if dentro de if)
* Número de estruturas de decisão

## Nomes significativos
* Escolha os nomes que revelem intenção
* Use nomes fáceis de se prever e encontrar
* Evitar siglas ou acrônimos
* Não economize palavras
* Evitar palavras reservadas
* Não misturar idioma (portuguẽs, inglẽs)

Fazer as seguintes perguntas quando for nomear algo:
* Por que existe
* O que faz
* Como é usado

## Boas práticas
Nomes de classes devem ser substantivos e não devem conter verbos:
```
CustomerRepository()
```

Nomes dos métodos devem conter verbos de preferência no infinitivo:
```
AddUser()
```

Não seja genérico:
```
ERRADOS:
// processa a folha de pagamento
Process()

// calcula o imposto de renda
Calculate()
```

## Menos é mais
* A primeira regra dos métodos é que eles devem ser pequenos. A segunda regra é que eles devem ser menores ainda.
* Método <= 20 linhas
* Linha <= 100 caractéres
* Classe <= 500 linhas

## Métodos
* Extraia trechos em métodos privados em uma classe, pois nem tudo que ele faz precisa estar público
* Métodos devem fazer apenas uma coisa, fazẽ-la certa e somente fazê-la
* Evite muitos parâmetros
* Não deixe o método mentir dizendo que faz uma coisa e faz outras "escondido"
* Se o método tiver mais de uma responsabilidade, extraia em dois ou mais
* Leia seu método de cima para baixo como uma narrativa, ele deve fazer sentido
* Aplique uma boa indentação

## Tratamento de erros
* Tratar e prever possíveis exceções é de responsabilidade do Dev
* Retorne exceptions e não código de erro
* Informe o máximo que puder em sua exception
* Se necessário crie exceptions personalizadas para um problema específico
* Não retorne null
* Regra dos escoteiros: "Deixe a área de acampamento mais do que como vocẽ a encontrou"
