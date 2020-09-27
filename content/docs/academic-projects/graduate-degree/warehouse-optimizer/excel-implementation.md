---
title: "Excel Implementation"
date: 2018-01-10
github: ""
weight: 1
draft: false
bookCollapseSection: true
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookComments: true
---

The Excel implementation relied on the use of OpenSolver (instead of the standard MS Excel Solver) and VBA macros that aided in the passage of information between pages and in the call of OpenSolver.

## Mathematical model
The mathematical model used was as follows
<center>{{<figure src="/images/projetos-academicos/licenciatura/otimizador-armazem/excel/01-modelo-matematico-excel.png">}}.</center>
<center>{{<figure src="/images/projetos-academicos/licenciatura/otimizador-armazem/excel/02-restricoes-matematico-excel.png">}}</center>

## Pages
Frontend: page that receives user input and where the user sees the result
<center>{{<figure src="/images/projetos-academicos/licenciatura/otimizador-armazem/excel/03-frontend.png">}}</center>

Backend: page responsible for the first part of the optimization process
<center>{{<figure src="/images/projetos-academicos/licenciatura/otimizador-armazem/excel/04-backend1.png">}}</center>

Backend_: page responsible for the second part of the optimization process
<center>{{<figure src="/images/projetos-academicos/licenciatura/otimizador-armazem/excel/05-backend2.png">}}</center>
