# Requisições de rede

> O que você vai aprender
> 
> - Como o Cypress permite que você crie stubs no backend com o [`cy.intercept()`](https://docs.cypress.io/api/commands/intercept)
> - Quais alterações fazemos quando adicionamos um stub em nossas > requisições de rede
> - Como o Cypress visualiza o gerenciamento de rede no Comando Log
> - Como usar apelidos para se referir a requisições e esperar por elas
> - Como escrever testes declarativos que resistem a flake

> Nota: Se você está procurando um recurso para fazer uma requisição HTTP, dê uma olhada em [`cy.request()`](https://docs.cypress.io/api/commands/request)

O Cypress ajuda você a testar todo o ciclo de vida das requisições HTTP em sua aplicação. O Cypress fornece acesso aos
objetos com informações sobre a requisição, permitindo que você faça asserções sobre suas propriedades. Além disso, 
você pode até mesmo criar um stub e simular a resposta de uma requisição.

Cenários de teste comuns:

- Asserção no corpo de uma requisição
- Asserção no url de uma requisição
- Asserção nos cabeçalhos de uma requisição
- Stub do corpo de uma resposta
- Stub do código de status de uma resposta
- Stub dos cabeçalhos de uma resposta
- Atrasando uma resposta
- Esperando que uma resposta aconteça

No Cypress, você tem a possibilidade de escolher se deseja fazer o stub das respostas ou permitir que elas cheguem ao
seu servidor. Você também pode misturar e combinar dentro do mesmo teste, escolhendo fazer o stub de certas requisições,
enquanto permite que outras acessem seu servidor.

Vamos investigar as duas estratégias, por que você usaria uma em relação à outra e por que deve usar ambas regularmente.

