---
title: "Java Comparation"
date: 2018-01-10
github: ""
weight: 5
draft: false
bookCollapseSection: true
# bookFlatSection: false
bookToc: false
# bookHidden: false
# bookComments: true
---

{{< columns >}}
Initial warehouse occupation
```
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
<--->
Solution for removing 5 elements
```
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
```
<--->
Occupation after changes
```
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
{{< /columns >}}