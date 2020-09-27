---
title: "Java Demonstration"
date: 2018-01-10
github: ""
weight: 4
draft: false
bookCollapseSection: true
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookComments: true
---
## Application execution
After running the application the menu is displayed. Let's start by listing the initial occupation.
```
================================================================================
Bem-vindo
Menu:
N) Nova Otimização
L) Listar Ocupação
F) Fechar a aplicação
Selcione uma das opções: L
================================================================================
Lista de Armazens
0) AR30: ARM LENG3
Especifique Armazém: 0
================================================================================
Lista de Areas Logicas
0) E1: (1000;500;0) x (1210;2900;0)
Especifique Aréa Lógica: 0
================================================================================
Lista de Corredores
0) C12: (1000;500;0) x (1210;2900;0)
Especifique Corredor: 0
    Baia 1        Baia 2
     1 2 3         1 2 3
01 | O X X |  '  | O O X |
02 | X O O |  '  | X O X |
03 | X X X |  '  | O X O |
04 | O X X |  '  | X X X |
05 | O X X |  '  | X X O |
06 | O O O |  '  | X X O |
07 | X O O |  '  | X X X |
08 | X X X |  '  | X X X |
09 | O X X |  '  | X O X |
10 | O X X |  '  | X O X |
11 | O O X |  '  | O O X |
12 | X X X |  '  | X O X |
13 | X X X |  '  | X X X |
14 | X O X |  '  | X X X |
15 | X X O |  '  | X X X |
16 | X X X |  '  | X X X |
17 | O X O |  '  | X X X |
18 | O O X |  '  | O X X |
19 | X X O |  '  | X X X |
20 | X X X |  '  | X O O |
```

Após isto vamos iniciar uma nova otimização. Neste caso será uma recolha e vamos solicitar uma quantidade impossível.
```
================================================================================
Bem-vindo
Menu:
N) Nova Otimização
L) Listar Ocupação
F) Fechar a aplicação
Selcione uma das opções: N
================================================================================
Lista de Armazens
0) AR30: ARM LENG3
Especifique Armazém: 0
================================================================================
Lista de Areas Logicas
0) E1: (1000;500;0) x (1210;2900;0)
Especifique Aréa Lógica: 0
================================================================================
Lista de Corredores
0) C12: (1000;500;0) x (1210;2900;0)
Especifique Corredor: 0
================================================================================
Lista de AGVs
0) KJ53 25 Apr 1918 23:00:00 GMT
Especifique AGV: 0
================================================================================
E uma Recolha? [N->Não / S->Sim]S
================================================================================
Lista de FNPs
0) FNP1: leite a vaca feliz(Aprovada)
1) FNP2: ovos a galinha que canta(Aprovada)
2) FNP3: fruta pomar saudavel(Aprovada)
3) FNP4: aspiradores tudo limpo(Aprovada)
4) FNP5: parafusos sempre fixo(Aprovada)
5) FNP6: porcas ferragens e ca(Aprovada)
6) FNP7: alface pomar saudavel(Aprovada)
7) FNP8: tomate pomar saudavel(Aprovada)
8) FNP9: chouriços enchidos da ericeira(Aprovada)
9) FNP10: smartphones ching-ling(Aprovada)
Especifique FNP: 3
================================================================================
Que quantidade de paletes pretende? 12
================================================================================
Resumo da otimização:
Armazem: ARM LENG3
Area Lógica: E1: (1000;500;0) x (1210;2900;0)
Corredor: C12: (1000;500;0) x (1210;2900;0)
AGV: KJ53       25 Apr 1918 23:00:00 GMT
FNP: FNP4: aspiradores(Aprovada)
Tipo: Recolha
Quantidade de paletes pedidas: 12
================================================================================
Pretende continuar?[N->Não / S->Sim]S
Quantidade inválida!
```

Vamos iniciar então uma otimização, mas desta vez válida
```
================================================================================
Bem-vindo
Menu:
N) Nova Otimização
L) Listar Ocupação
F) Fechar a aplicação
Selcione uma das opções: N
================================================================================
Lista de Armazens
0) AR30: ARM LENG3
Especifique Armazém: 0
================================================================================
Lista de Areas Logicas
0) E1: (1000;500;0) x (1210;2900;0)
Especifique Aréa Lógica: 0
================================================================================
Lista de Corredores
0) C12: (1000;500;0) x (1210;2900;0)
Especifique Corredor: 0
================================================================================
Lista de AGVs
0) KJ53 25 Apr 1918 23:00:00 GMT
Especifique AGV: 0
================================================================================
E uma Recolha? [N->Não / S->Sim]S
================================================================================
Lista de FNPs
0) FNP1: leite a vaca feliz(Aprovada)
1) FNP2: ovos a galinha que canta(Aprovada)
2) FNP3: fruta pomar saudavel(Aprovada)
3) FNP4: aspiradores tudo limpo(Aprovada)
4) FNP5: parafusos sempre fixo(Aprovada)
5) FNP6: porcas ferragens e ca(Aprovada)
6) FNP7: alface pomar saudavel(Aprovada)
7) FNP8: tomate pomar saudavel(Aprovada)
8) FNP9: chouriços enchidos da ericeira(Aprovada)
9) FNP10: smartphones ching-ling(Aprovada)
Especifique FNP: 0
================================================================================
Que quantidade de paletes pretende? 5
================================================================================
Resumo da otimização:
Armazem: ARM LENG3
Area Lógica: E1: (1000;500;0) x (1210;2900;0)
Corredor: C12: (1000;500;0) x (1210;2900;0)
AGV: KJ53       25 Apr 1918 23:00:00 GMT
FNP: FNP1: leite(Aprovada)
Tipo: Recolha
Quantidade de paletes pedidas: 5
================================================================================
Pretende continuar?[N->Não / S->Sim]S
Job Number : 8294242
Password   : jLHcwgDZ
Tempo da tarefa: 347 segundo

    Baia 1        Baia 2
     1 2 3         1 2 3
01 | O X O |  '  | O O O |
02 | O O O |  '  | O O O |
03 | O O O |  '  | O O O |
04 | O O O |  '  | O O O |
05 | O O O |  '  | O O O |
06 | O O O |  '  | O O O |
07 | O O O |  '  | X O O |
08 | O O O |  '  | O O O |
09 | O O O |  '  | O O X |
10 | O O O |  '  | O O O |
11 | O O O |  '  | O O O |
12 | O O O |  '  | O O O |
13 | O O O |  '  | O O O |
14 | O O X |  '  | O O O |
15 | O O O |  '  | O O O |
16 | O O O |  '  | O O O |
17 | O O O |  '  | X O O |
18 | O O O |  '  | O O O |
19 | O O O |  '  | O O O |
20 | O O O |  '  | O O O |

Pretende aplicar ao armazem?[N->Não / S->Sim]S
Alterações aplicadas!
```

Como é possivel observar foi solitada a autorização para aplicar as alterações e após o consentimento dado o resultado da listagem é o seguinte.
```
================================================================================
Bem-vindo
Menu:
N) Nova Otimização
L) Listar Ocupação
F) Fechar a aplicação
Selcione uma das opções: L
================================================================================
Lista de Armazens
0) AR30: ARM LENG3
Especifique Armazém: 0
================================================================================
Lista de Areas Logicas
0) E1: (1000;500;0) x (1210;2900;0)
Especifique Aréa Lógica: 0
================================================================================
Lista de Corredores
0) C12: (1000;500;0) x (1210;2900;0)
Especifique Corredor: 0
    Baia 1        Baia 2
     1 2 3         1 2 3
01 | O O X |  '  | O O X |
02 | X O O |  '  | X O X |
03 | X X X |  '  | O X O |
04 | O X X |  '  | X X X |
05 | O X X |  '  | X X O |
06 | O O O |  '  | X X O |
07 | X O O |  '  | O X X |
08 | X X X |  '  | X X X |
09 | O X X |  '  | X O O |
10 | O X X |  '  | X O X |
11 | O O X |  '  | O O X |
12 | X X X |  '  | X O X |
13 | X X X |  '  | X X X |
14 | X O O |  '  | X X X |
15 | X X O |  '  | X X X |
16 | X X X |  '  | X X X |
17 | O X O |  '  | O X X |
18 | O O X |  '  | O X X |
19 | X X O |  '  | X X X |
20 | X X X |  '  | X O O |

```