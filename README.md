# Филип Видиновски 175041

## 2.Control Flow Graph

![CFG](https://user-images.githubusercontent.com/38265146/170490266-f8a14b76-a3d5-4d1e-ae8c-37a619743186.png)

## 3.Пресметка на цикломатската комплексност на функцијата:

Цикломатска комплексност = E-N+2 = 29-25+2 = 6

N=16 – во графот има 25 јазли
E=19 – во графот има 29 рабови

## 4.Every Statement критериум

 - list = [0,#,0,#,0,#,0,#,0] - 1,2,3,5,6,8,9, 10,12,14,15,16,17,19,20,22,23,24,25, 10,12,13,25, 10,12,14,15,16,17,19,20,22,23,24,25, 10,12,13,25, 10,12,14,15,16,17,18,20,21,22,23,24,25, 10,12,13,25, 19,12,14,15,16,17,19,20,21,22,24,25, 10,12,13,25, 19,12,14,15,16,17,19,20,21,22,24,25, 10,11

Со овој тест случај, се изминуваат сите јазли освен тие што враќаат ислкучоци. Причината низата да е од големина 9 е за да се помине условот во 17 за да се пристапи до јазол 18, т.е. за еден број да биде опкружен со две мини (тараби) од бочните страни.
Изглед на низата:
0#0
#0#
0#0

Со претходниот тест случај логички не може да се поминат јазлите 4 и 7, па затоа се користат два други влезови.

 - list = [] - 1, 2, 4 - Со овој тест случај се исполнува случајот во кој листата е празна и се враќа исклучок.
 - list = [#,#] - 1, 2, 3, 5, 7 - Со овој случај се исполнува случајот во кој не е пратена низа чиј корен е цел број (должината на низата не е 4/9/16... елементи).

## 5.Every Branch критериум

- list = [0,#,0,0, #,0,#,0, 0,#,0,0, 0,0,0,#] -1,2,3,5,6,8,9, 10,12,14,15,16,17,19,20,22,23,24,25, 10,12,13,25, 10,12,14,15,16,17,19,20,22,23,24,25, 10,12,14,15,16,20,22,24,25, 10,12,13,25, 10,12,14,15,16,17,18,20,21,22,23,24,25, 10,12,13,25, 10,12,14,15,16,17,19,20,22,24,25, 10,12,14,15,16,17,19,20,21,22,24,25, 10,12,13,25, 10,12,14,15,16,17,19,20,21,22,24,25, 10,12,14,15,16,20,22,24,25, 10,12,14,15,16,20,22,24,25, 10,12,14,15,16,20,21,22,24,25, 10,12,14,15,16,17,19,20,22,24,25, 10,12,13,25, 10,11

0#00<br/>
#0#0<br/>
0#00<br/>
000#<br/>

1,2,3,5,6,8,9 - влез до for циклусот<br/>
10,12,14,15,16,17,19,20,22,23,24,25, - гранка за бомба до и под бројот<br/>
10,12,13,25, - гранка за бомба<br/>
10,12,14,15,16,17,19,20,22,23,24,25, - гранка за бомба до и под бројот<br/>
10,12,14,15,16,20,22,24,25, - гранка за 0 бомби околу бројот<br/>
10,12,13,25, - гранка за бомба<br/>
10,12,14,15,16,17,18,20,21,22,23,24,25, - гранка за бомби на сите 4 страни од бројот<br/>
10,12,13,25, - гранка за бомба<br/>
10,12,14,15,16,17,19,20,22,24,25, - проверка за бомба до бројот<br/>
10,12,14,15,16,17,19,20,21,22,24,25 - проверка за бомба до и над бројот<br/>
10,12,13,25, - гранка за бомба<br/>
10,12,14,15,16,17,19,20,21,22,24,25 - проверка за бомба до и над бројот<br/>
10,12,14,15,16,20,22,24,25, - гранка за 0 бомби околу бројот<br/>
10,12,14,15,16,20,22,24,25, - гранка за 0 бомби околу бројот<br/>
10,12,14,15,16,20,21,22,24,25 - гранка за бомба над бројот<br/>
10,12,14,15,16,17,19,20,22,24,25, - проверка за бомба до бројот<br/>
10,12,13,25, - гранка за бомба<br/>
10,11 - крај<br/>

Гранките 1,2,4 и 1,2,3,5,7 не можат логички да се поминат во исто време како сите други гранки
