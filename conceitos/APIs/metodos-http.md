# Métodos HTTP
Seguindo o princípio 4 - Interface Uniforme - cada recurso deve ser representado com um método HTTP específico e consistente em toda aplicação.

Os métodos mais utilizados pra cada situação são:

## GET
Retornar dados / recurso para o *cliente*

## POST
Criar um novo recurso

## PUT / PATCH
Atualizar um recurso

### PUT vs PATCH
* PUT
  Sobrescrever todo o recurso. Você deve enviar o payload do recurso inteiro.
* PATCH
  Atualizar apenas uma parte do recurso. Você só precisa enviar o que pretende atualizar.

## DELETE
Deletar um recurso
