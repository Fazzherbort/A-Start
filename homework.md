#  2020/09/28 作业
---
## T2.4

***(c.)*** 

$$letter1 \rightarrow$$ *a | b | c | d ......*  %%某语言中任意不为字符$$*$$的字符

$$letter2 \rightarrow$$ *a | b | c | d ......*  %%某语言中任意不为字符$$*$$和字符/的字符

$$comment \rightarrow$$ / $$*\ letter1^*$$  $$(*^+\ letter2\ letter1^*)^**^**$$ /

这就是某语言的注释的正规定义

***(d.)***

$$number0 \rightarrow$$ $$0$$

$$number1 \rightarrow$$ $$(1|0\ 1)\ (0\ 1)^*\ (0|\epsilon)\ |0$$

$$number2 \rightarrow$$ $$(2|number1\ 2)\ (number1\ 2)^*\ (number1|\epsilon)\ |number1$$

$$number3 \rightarrow$$ $$(3|number2\ 3)\ (number2\ 3)^*\ (number2|\epsilon)\ |number2$$

$$number4 \rightarrow$$ $$(4|number3\ 4)\ (number3\ 4)^*\ (number3|\epsilon)\ |number3$$

$$number5 \rightarrow$$ $$(5|number4\ 5)\ (number4\ 5)^*\ (number4|\epsilon)\ |number4$$

$$number6 \rightarrow$$ $$(6|number5\ 6)\ (number5\ 6)^*\ (number5|\epsilon)\ |number5$$

$$number7 \rightarrow$$ $$(7|number6\ 7)\ (number6\ 7)^*\ (number6|\epsilon)\ |number6$$

$$number8 \rightarrow$$ $$(8|number7\ 8)\ (number7\ 8)^*\ (number7|\epsilon)\ |number7$$

$$digits \rightarrow$$ $$(9|number8\ 9)\ (number8\ 9)^*\ (number8|\epsilon)\ |number8$$

这就是相邻数字都不相同的所有数字串的正规定义

---
## T2.7

***(d.)***

有$$a、b$$的NFA如下所示:

<div align=center>

![a](../HW1/figs/2.png)

![b](../HW1/figs/3.png)

<div align=left>

而$$(a|b)^*$$的NFA如下所示:

<div align=center>

![a|b](../HW1/figs/1.png)

<div align=left>

那么将两个$$(a|b)^*$$与$$abb$$的NFA相连接，即可得到$$(a|b)^*\ abb\ (a|b)^*$$的NFA如下所示:

<div align=center>

![](../HW1/figs/4.png)

<div align=left>

因此，当输入字符串$$ababbab$$时，状态转换序列为$$0\rightarrow1\rightarrow2\rightarrow4\rightarrow6\rightarrow1\rightarrow3\rightarrow5\rightarrow6\rightarrow7\rightarrow8\rightarrow9\rightarrow10\rightarrow11\rightarrow12\rightarrow14\rightarrow16\rightarrow11\rightarrow13\rightarrow15\rightarrow16\rightarrow17$$.

---
## T2.8

令$$A=\{0,1,2,3,7\}$$

有$$move(A,a)=\{4,8\}$$

则$$B=\epsilon-closure(move(A,a))=\{1,2,3,4,6,7,8\}$$

有$$move(A,b)=\{5\}$$

则$$C=\epsilon-closure(move(A,a))=\{1,2,3,5,6,7\}$$

有$$move(B,a)=\{4,8\}$$, 这时$$\epsilon-closure(move(B,a))$$已经被标记了

有$$move(B,b)=\{5,9\}$$

则$$D=\epsilon-closure(move(B,b))=\{1,2,3,5,6,7,9\}$$

有$$move(C,a)=\{4,8\}$$, 这时$$\epsilon-closure(move(C,a))$$已经被标记了

有$$move(C,b)=\{5\}$$, 这时$$\epsilon-closure(move(C,b))$$已经被标记了

有$$move(D,a)=\{4,8\}$$, 这时$$\epsilon-closure(move(D,a))$$已经被标记了

有$$move(D,b)=\{5,10\}$$

则$$E=\epsilon-closure(move(D,b))=\{1,2,3,5,6,7,10,11,12,13,17\}$$

有$$move(E,a)=\{4,8,14\}$$

则$$F=\epsilon-closure(move(E,a))=\{1,2,3,4,6,7,8,11,12,13,14,16,17\}$$

有$$move(E,b)=\{5,15\}$$

则$$G=\epsilon-closure(move(E,b))=\{1,2,3,5,6,7,11,12,13,15,16,17\}$$

有$$move(F,a)=\{4,8,14\}$$, 这时$$\epsilon-closure(move(F,a))$$已经被标记了

有$$move(F,b)=\{5,9,15\}$$

则$$H=\epsilon-closure(move(F,b))=\{1,2,3,5,6,7,9,11,12,13,15,16,17\}$$

有$$move(G,a)=\{4,8,14\}$$, 这时$$\epsilon-closure(move(G,a))$$已经被标记了

有$$move(G,b)=\{5,15\}$$, 这时$$\epsilon-closure(move(G,b))$$已经被标记了

有$$move(H,a)=\{4,8,14\}$$, 这时$\epsilon-closure(move(H,a))$$已经被标记了

有$$move(H,b)=\{5,10,15\}$$

则$$I=\epsilon-closure(move(H,b))=\{1,2,3,5,6,7,10,11,12,13,15,16,17\}$$

有$$move(I,a)=\{4,8,14\}$$, 这时$$\epsilon-closure(move(I,a))$$已经被标记了

有$$move(I,b)=\{5,15\}$$, 这时$$\epsilon-closure(move(I,b))$$已经被标记了

有DFA的转换表如下所示:

||a|b|
|-|-|-|
|A|B|C|
|B|B|D|
|C|B|C|
|D|B|E|
|E|F|G|
|F|F|H|
|G|F|G|
|H|F|I|
|I|F|G|


故相应的DFA如下所示:

<div align=center>

![](../HW1/figs/5.png)

<div align=left>

因此，当输入字符串$$ababbab$$时，状态转换序列为$$A\rightarrow B\rightarrow D\rightarrow B\rightarrow D\rightarrow E\rightarrow F\rightarrow H$$

---
## T2.12
***(b.)***

有$$(a|b)^*\ a\ (a|b)\ (a|b)$$的NFA如下所示:

<div align=center>

![](../HW1/figs/6.png)

<div align=left>

NFA转换为DFA如下所示：

$$A=\{0,1,2,3,7\}$$

$$B=\{1,2,3,4,6,7,8,9,10\}$$

$$C=\{1,2,3,5,6,7\}$$

$$D=\{1,2,3,4,6,7,8,9,10,11,13,14,15\}$$

$$E=\{1,2,3,5,6,7,12,13,14,15\}$$

$$F=\{1,2,3,4,6,7,8,9,10,11,13,14,15,18\}$$

$$G=\{1,2,3,5,6,7,13,14,15,18\}$$

$$H=\{1,2,3,4,6,7,8,9,10,18\}$$

$$I=\{1,2,3,5,6,7,18\}$$

转换表如下所示:

||a|b|
|-|-|-|
|A|B|C|
|B|D|E|
|C|B|C|
|D|F|G|
|E|H|I|
|F|F|G|
|G|H|I|
|H|D|G|
|I|B|C|

进行化简:

将上面的个集合划分为$$S-F=\{A,B,C,D,E\}$$和$$F=\{F,G,H,I\}$$

之后$$\{A,B,C,D,E\}$$可以划分为$$\{A,C\}、\{B\}、\{D\}、\{E\}$$，而$$\{F,G,H,I\}$可以划分为$$\{F\}、\{G\}、\{H\}、\{I\}$$，可以用$$\{A\}$$来代替$$\{A,C\}$$

故$$(a|b)^*\ a\ (a|b)\ (a|b)$$的最简DFA如下所示:

<div align=center>

![](../HW1/figs/7.png)

<div align=left>


---


