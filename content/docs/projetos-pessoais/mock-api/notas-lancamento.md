---
title: "Notas Lançamento"
weight: 1
github: ""
bookCollapseSection: false
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookComments: true
---

# Release 2.1
### Change Log
- Correção do erro no restauro dos endpoints
- Os endpoints são agora corrigidos (convertidos em minusculas e removendo o ```/``` do final)

### Knowned Issues
- Nas rotas **/mocks** e **/mocks/watch** a animação de carregamento
- Se o request for feito com um endpoint válido mas acabado com ```/``` o serviço retorna a resposta do metodo GET no lugar da que foi pedida

### Quer ajudar?
Faça um pull request com as alterações que considere uteis, abra um issue no GitHub ou contacte-me pelos outros canais.
---

## Release 2.0
Este segundo lançamento é focado em organização interna de código e migração da interface web para Vue.JS e Laravel Mix

### Change Log
- Novo endpoint para listar detalhes dos endpoints
- Mudanças internas de código para aumentar encapsulamento
- Nova interface web feita em Vue.JS e Laravel Mix
- **/mocks** e **/mocks/watch** usam os endpoints **api/mgmt** para apresentar a informação
- Nenhuma view usa controladores Laravel

### Problemas conhecidos
- Nas rotas **/mocks** e **/mocks/watch** a animação de carregamento
- Funcionalidade de restauro de endpoints não esta a funcionar

### Quer ajudar?
Faça um pull request com as alterações que considere uteis, abra um issue no GitHub ou contacte-me pelos outros canais.

---

## First Release
Primeiro lançamento

### Funcionalidades de Mock:
* Obter as respostas gravadas para um endpoint
* Criar endpoints
* Atualizar endpoints
* Ativar/Inativar endpoint
* Apagar endpoints

### Funcionalidades de Gestão:
* Obter todos os endpoints
* Criar vários endpoints ao mesmo tempo

### Funcionalidade da UI:
* Start Guide
* Listagem de todos os endpoints
* Apresentar as propriedades dos endpoints

### Testar
Dentro da pasta tests existe uma outra pasta chamada Postman com uma coleção para fazer testes e exemplos de uso