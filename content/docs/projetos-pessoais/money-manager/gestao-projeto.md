---
title: "Gestao de Projeto"
weight: 2
bookCollapseSection: false
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookComments: true
---
# Organização do repositório
O repositório irá conter 3 branches principais. Estas servirão para separar o código fonte do projeto nos seus principais estados: Desenvolvimento, Testes e Produção. Conforme a figura a baixo, a branch **Develop** corresponde ao estado de desenvolvimento, **Staging** ao estado de testes e por fim a **Master** corresponde ao estado de produção.

{{<figure src="/images/money-manager/0.0_Source-Code-Management-Protocol.png">}}
 
É possível ainda notar que existem algumas branches criadas a partir da develop. Estas são branches de feature, ou seja, novas funcionalidades que serão incorporadas no código no futuro. Estas apenas são inluídas na branch develop quando são consideradas prontas [ver definição de pronto]. Após todas a funcionalidade concluídas, é feito um merge para Staging e é aqui onde a aplicação é testada num ambiente mais próximo ao que terá em produção e são procurados problemas na utilização da aplicação. Concluída esta fase é feito um pull da Master para verificar que nenhuma alteração corrompeu a aplicação. Caso esteja tudo bem as alterações são enviadas para Master e para Develop para que todas as branchs se sincronizem.
Todos os desenvolvimento devem começar na branch Develop a menos que se trate de um hot fix.
 
## Organização e nomenclatura das branches  
- Master--------------------> Master  
    - Staging---------------> Staging  
        - Hot Fix ---------> hf/< nome do hot fix >  
    - Develop --------------> Develop  
        - Feature ---------> feature/< nome da feature >  
 
### Branch de Hot Fix  
Um hot fix é uma atualização para corrigir um problema detetado em produção. O procedimento para criar 1 hot fix será fazer um pull da Master para Staging e aqui criar uma nova branch de hot fix. Quando se considerar o hot fix pronto, este deve voltar para Staging, ser testado e no final ser enviado para a Master e Develop
 
# Definição de pronto
A definição de pronto varia um pouco entre os diferentes estados da aplicação.
 
## Desenvolvimento de uma funcionalidade
Considera-se que algo está pronto quando:
1. Tem o comportamento esperado
2. Passou nos testes de funcionalidade e unitários.  
Após isto este código pode ser incluído na branch Develop.
 
## Desenvolvimento de um hot fix
Considera-se que algo está pronto quando:
1. Correção do problema que originou o hot fix
2. Passou nos testes de funcionalidade e unitários.  
Após isto este código pode ser incluído na branch Staging.
 
## Desenvolvimento
Considera-se que algo está pronto quando:
1. Contem as funcionalidades que foram planeadas para a release.
2. Passou nos testes de funcionalidade e unitários.  
Após isto este código pode ser incluído na branch Staging.
 
## Staging
Considera-se que algo está pronto quando:
1. Contem as funcionalidades que foram planeadas.
2. Cumpre os requisitos da release.  
Passou nos testes de funcionalidade e unitários.