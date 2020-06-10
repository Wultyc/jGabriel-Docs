---
title: "Demonstração da ferramenta em Excel"
date: 2018-01-10
github: ""
weight: 2
draft: false
bookCollapseSection: true
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookComments: true
---

## Inicializaão
O utilizador começa por preecnher a ocupação do armazém. Depois disso define o número de paletes que pretende, o tempo máximo para a execução e a velocidade do AGV. Em seguida pressiona o botão otimizar.
{{<figure src="/images/projetos-academicos/licenciatura/otimizador-armazem/excel/demonstracao/0.png">}}

## Primeiro resultado
Poucos segundos depois o resultado é apresentado
{{<figure src="/images/projetos-academicos/licenciatura/otimizador-armazem/excel/demonstracao/1-1.png">}}

Nas páginas de backend aparecem os resultados intermédios dos cálculos para a otimização
{{< columns >}}
{{<figure src="/images/projetos-academicos/licenciatura/otimizador-armazem/excel/demonstracao/1-2.png">}}
<--->
{{<figure src="/images/projetos-academicos/licenciatura/otimizador-armazem/excel/demonstracao/1-3.png">}}
{{< /columns >}}

## Segundo resultado
A aplicação é iterativa, o que quer dizer que é possivel usar os resultados da ultima otimização para inicar um novo processo, e foi isso que se fez.
{{<figure src="/images/projetos-academicos/licenciatura/otimizador-armazem/excel/demonstracao/2-1.png">}}

## Terceiro resultado
Voltando a executar, mas neste caso fazendo um pedido impossivel de satizfazer a aplicação apresenta uma mensagem de erro.
{{<figure src="/images/projetos-academicos/licenciatura/otimizador-armazem/excel/demonstracao/3-1.png">}}
{{<figure src="/images/projetos-academicos/licenciatura/otimizador-armazem/excel/demonstracao/4.png">}}