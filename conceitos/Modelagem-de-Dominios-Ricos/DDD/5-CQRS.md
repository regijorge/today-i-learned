# CQRS - Command Query Responsibility Segregation
* É um padrão arquitetural onde o foco principal é separar os meios de leitura e escrita de dados. Alterações de dados vão ser feitas via **commands** e leitura de dados são realizados via **queries**
* O objetivo do CQRS é prover expressividade para a aplicação, pois todos os commands representam uma intenção de negócio
* Promove a consistência eventual, que é quando possuímos um banco de leitura e outro de escrita com os mesmos dados, porém os dados não são consistidos exatamente no mesmo momento
* Muito aplicado em arquiteturas hexagonais, microservices ou em aplicações que produzem uma alta demanda de consumo de dados

### Commands
* Representam uma intenção de mudança no estado de uma entidade
* São expressivos e representam uma intenção de negócio ex: *AumentarSalarioFuncionarioCommand*

### Queries
* É a forma de obter dados de um banco ou origem de dados para atender as necessidades da aplicação

## Teorema CAP (Consistency, Availability, Partition Tolerance)
* Consistência
* Disponibilidade, escalabilidade
* Tolerância à falhas

Só é possível combinar 2 das 3 opções
O ideal é unir Disponibilidade e tolerância

## Como sincronizar as bases?
### Síncrono
* Todo comando gera atualizações síncronas

### AsSíncrono
* Todo comando gera atualizações assíncronas

### Agendado
* Um processo roda periodicamente e gera as atualizações

### Por demanda
* As atualizações são geradas via request (se os dados forem antigos)

## Command Stack - Query Stack

## Utilização de Sagas
