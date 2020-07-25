---
title: "Implementação em Java e AMPL"
date: 2018-01-10
github: ""
weight: 3
draft: false
bookCollapseSection: true
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookComments: true
---

A implementação em Java tinha como objetivo atingir os mesmos resultados que a ferramenta anterior, mas desta vez usando AMPL para o processo de otimização. Aqui o grupo distinguiu-se dos restantes pois optou por utilizar a API pública do NEOS Server para efetuar a otimização.

## Principio da aplicação
A aplicação Java seria responsável por manter uma lista das posições das diferentes paletes de produtos. Quando o utilizador solicitasse que fosse feita uma otimização, a aplicação encarregar-se-ia de transformar a informação que tinha armazenda num formato compatível com AMPL e fazer a ligação ao servdior NEOS para solicitar a resolução do problema. Quando recebesse a resposta, apresentava ao utilizador e perguntava se este pretendia aplicar as alterações. Em caso afirmativo aplicava as alterações e devolvia o comando para o utilizador.

## Resolução de problemas anteriores
A estruturação desta aplicação pressupunha a existência de um outro projeto realizado em outra unidade corricular e que o grupo não possuia. Após expor o problema aos docentes e na inexistência de um projeto base que podesse ser fornececido pelos docentes, o grupo optou por uma solução de remedeio para a situação. Esse projeto anterior serviria para popular a aplicação em Java com dados para serem usados na otimização e não havendo tempo para fazer esse projeto, o grupo decidiu escrever as instruções para popular a aplicação na classe e assim poder cumprir o obejtivo final. Não foi a solução ideal, mas tendo em conta o curto tempo para a entrag do projeto e não se tratando do objeto de avalição esse caminho acabou por ser o escolhido. 