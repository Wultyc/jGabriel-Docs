---
title: "Solução Proposta"
date: 2020-06-11T21:19:22+01:00
github: ""
weight: 30
draft: false
bookCollapseSection: false
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookComments: true
---
Foram propostas várias soluções com diferentes combinações de produtos e serviços, alguns deles comerciais, mas a escolha final acabou por ser construir uma aplicação nova em PHP com o framework Laravel utilizando uma base de dados Microsoft SQL Server (devido à familiaridade que ja existia com o produto). Esta aplicação iria ser executada num servidor provisionado pela propria empresa.

Esta aplicação teria de corresponder a um lista de requisitos dos quais se destaca:
- Acesso apenas na rede local
- Existência de uma área de administração restrita
- A implementação teria de ser feita em duas fases:
    - A primeira onde se substitução totalmente a aplicação existente na fabrica (Registo de ponto, de recolhas, de produção, de produto acabado e de saída de produto acabado);
    - A segunda fase durante a qual as novas funcionalidades seriam aplicadas incrementalmente;

# Estrutura da nova aplicação

## Base de Dados
O primeiro passo foi definir o modelo de dados. Este teve como base o que ja existia mas com algumas modificações que auxiliassem na coesão da informação com o mínimo do impacto na performance.

## Aplicação
A Aplicação foi dividida em duas sub-aplicações diferentes:
- A aplicação de fabrica, utilizada pelos trabalhadores para fazer os registos. As rotas desta aplicação ficam dentro de ```/Fabrica/``` 
- O painel de administração, utilizada pelos administradores para gerir os registos. As rotas desta aplicação ficam dentro de ```/Painel/``` 

## As Stored Procedures
A opção por este recurso esteve relacionado com a familiaridade com o Sistema de Gestão de Base de DaDOS, o Microsoft SQL Server. Deste modo estes modulos poderiam ser criados, atualizados, apagados sem necessidade de conhecimento em PHP/Laravel para modificar a aplicação.