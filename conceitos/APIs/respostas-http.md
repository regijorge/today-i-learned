# Respostas HTTP

## Referências
* [HTTP Status Codes
](https://restfulapi.net/http-status-codes/)

## Código de Status
### 2×× Sucesso
Indica que a solicitação do **cliente** foi aceita com sucesso.

#### 200 - *OK*
Indica que a API REST executou com êxito qualquer ação solicitada pelo cliente.

Deve incluir um *response body*. As informações retornadas dependem do método usado na solicitação, por exemplo:

* GET: uma entidade correspondente ao recurso solicitado é enviada na resposta
* POST: uma entidade que descreve ou contém o resultado da solicitação.

#### 201 - *Created*
Sempre que um **recurso** é criado dentro de uma **coleção**.

O **servidor** DEVE criar o recurso antes de retornar o código de status **201**. Se a ação não puder ser realizada imediatamente, o **servidor** DEVE responder com uma resposta **202**.

#### 202 - Accepted
Normalmente usada para ações que demoram muito tempo para serem processadas. Indica que a solicitação foi aceita para processamento, mas o processamento não foi concluído. A solicitação pode ou não ser atendida ou talvez não permitida quando o processamento ocorre.

A **entidade** retornada com esta resposta DEVE incluir uma indicação do status atual da solicitação e um indicador para um monitor de status - *job queue location* - ou alguma estimativa de quando o usuário pode esperar que a solicitação seja atendida.

#### 204 - *No Content*
Geralmente é enviado em resposta a uma solicitação PUT, POST ou DELETE quando a API se recusa a enviar de volta qualquer mensagem ou representação de status no *response body*.

NÃO DEVE incluir mensagem no corpo e, portanto, é sempre encerrada pela primeira linha vazia após os campos do **cabeçalho**.

### 3×× Redirecionamento
Indica que o **cliente** deve executar alguma ação adicional para concluir sua solicitação.

#### 301 - Moved Permanently
Indica que um novo **URI** permanente foi atribuído ao recurso solicitado pelo cliente. A API REST deve especificar o novo URI no *header location* da resposta e todas as solicitações futuras devem ser direcionadas para o URI fornecido.

Você dificilmente usará esse código de resposta na sua API, pois sempre poderá usar o versionamento da API para a nova API, mantendo a antiga.

#### 302 - Found
É uma maneira comum de executar o redirecionamento de URL. Deverá ser fornecida uma URL no campo de *header location*.

#### 303 - See Other
Indica que um recurso do controlador concluiu seu trabalho, mas em vez de enviar um *response body* potencialmente indesejado, ele envia ao cliente o URI de um recurso de resposta. A resposta pode ser o URI da mensagem de status temporária ou o URI para algum recurso já existente e mais permanente.

Permite que uma API REST envie uma referência a um recurso sem forçar o cliente a baixar seu estado. Em vez disso, o cliente pode enviar uma solicitação GET para o valor do *header location*.

NÃO DEVE ser armazenada em cache, mas a resposta à segunda solicitação (redirecionada) pode ser armazenada em cache.

#### 304 - Not Modified
É semelhante a **204**, pois o *response body* deve estar vazio. A diferença é que **204** é usado quando não há nada a ser enviado no corpo, enquanto 304 é usado quando o recurso não foi modificado desde a versão especificada pelos cabeçalhos de solicitação *If-Modified-Since* ou *If-None-Match*.

Nesse caso, não há necessidade de retransmitir o recurso, pois o cliente ainda possui uma cópia baixada anteriormente.

Usar isso economiza banda e reprocessamento no servidor e no cliente, pois apenas os dados do cabeçalho devem ser enviados e recebidos.

#### 307 - Temporary Redirect
Indica que a API REST não processará a solicitação do cliente. Em vez disso, o cliente deve reenviar a solicitação ao URI especificado no *header location* da  resposta. No entanto, solicitações futuras ainda devem usar o URI original.

Uma API REST pode usar esse código de status para atribuir um URI temporário ao recurso solicitado pelo cliente. Por exemplo, uma resposta 307 pode ser usada para mudar uma solicitação do cliente para outro host.

O URI temporário DEVE ser fornecido pelo campo Localização na resposta. A menos que o método de solicitação foi HEAD, a entidade da resposta DEVE conter uma pequena nota de hipertexto com um hiperlink para os novos URI (s). Se o código de status 307 for recebido em resposta a uma solicitação que não seja GET ou HEAD, o agente do usuário NÃO DEVE redirecionar automaticamente a solicitação, a menos que possa ser confirmada pelo usuário, pois isso pode alterar as condições sob as quais a solicitação foi emitida.

### 4×× Erro Cliente
Indica que o **cliente** cometeu algum erro

#### 400 - Bad Request
Usado quando nenhum outro código de erro 4xx é apropriado. Os erros podem ser:
* Sintaxe mal formatada
* Parâmetros inválidos
* Roteamento enganoso
* etc...

O cliente não deve repetir o pedido sem modificações.

#### 401 - Unauthorized
Indica que o cliente tentou operar em um recurso protegido sem fornecer a autorização adequada. Pode ter fornecido as credenciais erradas ou nenhuma. A resposta deve incluir um campo de cabeçalho *WWW-Authenticate* contendo um desafio aplicável ao recurso solicitado.

O cliente pode repetir o pedido com um campo de cabeçalho de autorização adequado. Se a solicitação já incluía credenciais de autorização, a resposta 401 indica que a autorização foi recusada para essas credenciais. Se a resposta 401 contém o mesmo desafio que a resposta anterior, e o agente do usuário já tentou a autenticação pelo menos uma vez, então o usuário DEVE ser apresentada a entidade que foi dada na resposta, já que essa entidade pode incluir informações de diagnóstico relevantes.

#### 403 - Forbidden
Indica que a solicitação do cliente está formada corretamente, mas a API REST se recusa a cumpri-la, ou seja, o usuário não tem as permissões necessárias para o recurso. Uma resposta *403* não é um caso de credenciais de cliente insuficientes; isso seria *401* ("Não autorizado").

Autenticação não vai ajudar, e o pedido não deve ser repetido. Diferente de uma resposta 401, a autenticação não fará diferença.

#### 404 - Not Found
Indica que a API REST não pôde retornar um *recurso* solicitado.

Nenhuma indicação é dada sobre se a condição é temporária ou permanente. O código de status *410 - GONE* DEVE ser usado se o servidor souber, de alguma forma, que um recurso antigo está permanentemente indisponível e não possui endereço de encaminhamento. Esse código de status é comumente usado quando o servidor não deseja revelar exatamente por que a solicitação foi recusada ou quando nenhuma outra resposta é aplicável.

#### 405 - Method Not Allowed
Indica que o cliente tentou usar um método HTTP que o recurso não permite. Por exemplo, um recurso somente leitura pode suportar apenas GET e HEAD, enquanto um recurso do controlador pode permitir GET e POST, mas não PUT ou DELETE.

Uma resposta 405 deve incluir o cabeçalho *Allow*, que lista os métodos HTTP que o recurso suporta. Por exemplo:

```
Allow: GET, POST
```

#### 406 - Not Acceptable
Indica que a API não pode gerar nenhum dos tipos de mídia solicitados pelo cliente, conforme indicado pelo cabeçalho de solicitação *Accept*.

Por exemplo, uma solicitação do cliente para dados formatados como: <code>application/xml</code> receberá uma resposta 406 se a API estiver disposta apenas a formatar dados como: <code>application/json</code>.

#### 412 - Precondition Failed
Indica que o cliente especificou uma ou mais condições prévias em seus cabeçalhos de solicitação, dizendo efetivamente à API REST para executar sua solicitação apenas se determinadas condições forem atendidas. Uma resposta 412 indica que essas condições não foram atendidas; portanto, em vez de executar a solicitação, a API envia esse código de status.

#### 415 - Unsupported Media Type
Indica que a API não pode processar o tipo de mídia fornecido pelo cliente, conforme indicado pelo cabeçalho da solicitação *Content-type*.

Por exemplo, uma solicitação do cliente incluindo dados formatados como <code>application/xml</code> receberá uma resposta 415 se a API estiver disposta apenas a processar dados formatados como <code>application/json</code>.

Por exemplo, o cliente carrega uma imagem como <code>image /svg+xml</code>, mas o servidor exige que as imagens usem um formato diferente.

### 5×× Erro Servidor
Indica que o **servidor** cometeu algum erro

#### 500 - Internal Server Error
500 é a resposta de erro genérica da API REST. A maioria das estruturas da web responde automaticamente com esse código de status sempre que executa algum código que gera uma exceção.

Um erro 500 nunca é culpa do cliente e, portanto, é razoável que o cliente tente novamente a mesma solicitação que acionou essa resposta e espere obter uma resposta diferente.

#### 501 - Not Implemented
O servidor não reconhece o método de solicitação ou não possui a capacidade de atender à solicitação. Geralmente, isso implica disponibilidade futura, por exemplo: um novo recurso de uma API.
