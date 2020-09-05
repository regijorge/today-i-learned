# REST / RESTful

## REST
*Representational State Transfer* - **Transferência Representacional de Estado**.

É um **estilo de arquitetura de software** que consiste em um conjunto de princípios que podem ser aplicados ao criar um *web service*.

## RESTful
Quando um sistema aplica os princípios de REST, ele é chamado de RESTful.

## Princípios do REST
### 1) *Client-Server* - Cliente-Servidor
A interface do usuário e os dados armazenados são independentes entre sí.

### 2) *Stateless* - Sem estado
Cada solicitação do *cliente* para o *servidor* deve conter todas as informações necessárias para entender a solicitação e não pode tirar proveito de nenhum contexto armazenado no servidor. O estado da sessão é, portanto, mantido inteiramente no cliente.

### 3) *Cacheable* - Armazenável em cache
Toda resposta do *servidor* deve ser rotulada como "armazenável ​​em cache" ou "não armazenável em cache"

Se uma resposta for armazenável em cache, o cache do *cliente* poderá reutilizar esses dados de resposta para solicitações posteriores equivalentes.

### 4) *Uniform interface * - Interface uniforme
Para obter uma interface uniforme, são necessárias várias restrições arquiteturais para orientar o comportamento dos componentes.
O REST é definido por quatro restrições de interface: *
1) Identificação de recursos
2) Manipulação de recursos através de representações
3) Mensagens auto-descritivas
4) Hipermídia como o mecanismo do estado do aplicativo

A restrição da **interface uniforme** é parcialmente resolvida pela combinação de URIs e verbos HTTP e pelo uso deles de acordo com os padrões e convenções.

### 5) Layered system - Sistema em camadas
O estilo do sistema em camadas permite que uma arquitetura seja composta de camadas hierárquicas, restringindo o comportamento do componente, de modo que cada componente não possa "ver" além da camada imediata com a qual está interagindo.

### 6) Code on demand - Código sob demanda (opcional)
O REST permite que a funcionalidade do cliente seja estendida baixando e executando o código na forma de applets ou scripts. Isso simplifica os clientes, reduzindo o número de recursos necessários para a pré-implementação.
