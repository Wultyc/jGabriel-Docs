---
title: "Arquitetura do Sistema"
date: 2020-06-11T16:40:57+01:00
github: ""
weight: 10
draft: false
bookCollapseSection: false
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookComments: true
---

O sistema como um todo funcionava de um modo muito simples e era composto por três elementos:
- Os módulos: usados para fazer a leitura de sinais vitais e comunicar essa informação para a Microwells Box.
- Microwell Box: Um dispositivo onde os diferentes módulos poderiam ser conectados. Iria recolher a informação dos módulos e enviar-la para o serviço cloud.
- Miocrowell Cloud: Um serviço cloud para o armazenamento dos dados lidos para consulta futura. 

{{<figure src="/images/projetos-academicos/licenciatura/microwells/architecture.jpg" caption="Esquema de funcionamento do sistema" >}}