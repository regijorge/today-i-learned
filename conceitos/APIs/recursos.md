# *Resource* - Recurso

## Referências
https://restfulapi.net/resource-naming/

## O que é um recurso?

Um recurso pode contar sub-coleções

```
Collection resource
/customers
```

```
Singleton resource
/customers/{customerId}
```

```
Sub-collection resource
/customuers/{customerId}/accounts
```

```
Singleton resource
/customers/{customuerId}/accounts/{accountId}
```

## Nomenclatura de recursos
* Utilize **substantivos** indicando algo, ao invés de **verbos** indicando ação. Pois **substantivos** podem possuir **propriedades**, o que **verbos** não tem ex:
  * Usuários da plataforma
  * Contas do usuário da plataforma
