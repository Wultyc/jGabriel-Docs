---
title: "Modelo Dados"
weight: 4
bookCollapseSection: false
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookComments: true
---
# Estrutura de tabelas
Em seguida, é apresentado o modelo da base de dados. A maioria das tabelas refere-se diretamente a uma das entidades descritas anteriormente. As restantes foram definidas para fazer a ponte de ligação entre utilizadores e contas com respetivos cargos, utilizadores e organizações com respetivos cargo se por fim a ponte entre a lista de cargos e as permissões.
{{<figure src="/images/money-manager/4.1_db-model.png">}}

# Informações sobre as tabelas
Maioritariamente, a estrutura das tabelas é explicativa por si só, mas sobram algum pontos que vão ser incluídos nos requisitos do projeto:
 
## Accounts
Nesta tabela existe uma coluna chamada current_period que servirá para gravar o ciclo contabilístico do ultimo registo desta conta. Este valor servira para preencher automaticamente o campo transaction_period da tabela Transactions.
 
## Categories
Nesta tabela existe uma coluna chamada parent_category_id que servirá para incluir um ID desta mesma tabela. Este recurso servirá para criar uma hierarquia entre categorias. Esta hierarquia não deverá ter mais do que 1 nível, isto é, só existem categorias e sub-categorias.
Ainda nesta tabela existe uma coluna chamada transaction_type. Esta coluna servirá para identificar o tipo de movimento com o qual a categoria se relaciona, isto é, se é uma receita, despesa, transferência, etc... Neste caso os valores que podem ser incluídos são: "Revenue", "Expenses", "Savings", "Transfer".
 
## Transactions
Nesta tabela existe uma coluna chamada planed_expense deverá apenas conter valores "yes" ou "no".
A coluna transfer_transaction_id servirá apenas para gravar o ID da outra transação relacionada com esta. Os campos balance_before e balance_after são armazenados para evitar um sobre-processamento destes valores.
A coluna transaction_period servirá para identificar a que ciclo contabilístico se refere aquele movimento.
 
