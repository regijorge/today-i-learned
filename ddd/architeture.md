# Arquitetura
* Devemos separar os problemas da nossa aplicação em camadas bem definidas.

## Dependencie Inversion Principle - DIP
![alt text](https://dzone.com/storage/temp/4436217-kolka.png "Onion Architeture")

* Uma camada inferior nunca deve depender de uma superior, ambos dependem de abstração
* Abstração não deve depender de detalhes, detalhes é que devem depender de abstração

## Entity / Entidade
Desenhamos um conceito de domínio como entidade quando existe uma importância de forma individual e quando temos que distinguir de todos os objetos

## Value Object / Objeto de valor
É um pequeno objeto que representa uma simples entidade mas que não possui um identificador. Dois objetos de valor são iguais quando seus valores são os mesmos

## Objetos ricos vs Objetos anếmicos
A diferença entre os dois é que com objetos ricos, cada objeto esconde seus detalhes internos e tem responsabilidades sobre seus dados.

