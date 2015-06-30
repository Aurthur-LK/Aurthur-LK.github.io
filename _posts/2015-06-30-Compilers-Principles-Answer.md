---
layout: post
title: Compilers Principles Practice's Answer
category: Technical
tags: Html
description: Compilers Principles Practice's Answer
---

##本资料如有错误，欢迎直接指正，期待你的 pull request。


# 2.2 节的练习

### 2.2.1

考虑下面的上下文无关文法：

S -> S S + | S S * | a

1. 试说明如何使用该文法生成串 aa+a*
2. 试为这个串构造一颗语法分析树
3. 该文法生成的语言是什么？试证明

#### 解答

1. `S` -> `S` S * -> `S` S + S * -> a `S` + S * -> a a + `S` * -> a a + a *
2. ![语法树](https://raw.github.com/fool2fish/dragon-book-practice-answer/master/ch02/2.2/assets/2.2.1-2.png)
3. 把 a 看成是运算数，L = {支持加法和乘法的表达式的后缀表示形式}

### 2.2.2

下面各个文法生成什么语言？证明你的每一个答案

1.  S -> 0 S 1 | 0 1
2.  S -> + S S | - S S | a
3.  S -> S ( S ) S | ε
4.  S -> a S b S | b S a S | ε
5.  S -> a | S + S | S S | S * | ( S )

#### 解答

1. L = {0<sup>n</sup>1<sup>n</sup> | n>=1}
2. L = {支持加法和减法的表达式的前缀表达形式}
3. L = {匹配括号的任意排列和嵌套的括号串，包括 ε}
4. L = {数量相同的a和b组成的符号串，包括 ε}
5. ？

### 2.2.3

上一题中哪些文法具有二义性

#### 解答

1. 没有
2. 没有
3. 有

![二义语法树](https://raw.github.com/fool2fish/dragon-book-practice-answer/master/ch02/2.2/assets/2.2.3-3.png)

4. 有

![二义语法树](https://raw.github.com/fool2fish/dragon-book-practice-answer/master/ch02/2.2/assets/2.2.3-4.png)

5. 有

![二义语法树](https://raw.github.com/fool2fish/dragon-book-practice-answer/master/ch02/2.2/assets/2.2.3-5.png)

### 2.2.4

为下面的各个语言构建无二义性的上下文无关文法。证明你的文法都是正确的。

1. 用后缀方法表示的算数表达式
2. 由逗号分隔开的左结合的标识符列表(标识符以 id 表示，以下同)
3. 由逗号分隔开的右结合的标识符列表
4. 有整数、标识符、4个二目运算符 +, -, *, / 构成的算数表达式
5. ! 在上一题的运算符中增加单目+ 和单目-构成的算数表达式

#### 解答

1.  E -> E E op | num
2.  list -> list , id | id
3.  list -> id , list | id
4.  expr -> expr + term | expr - term | term

term -> term * factor | term / factor | factor

factor -> id | num | (expr)

5.  **注：**单目加减运算的优先级最高

expr -> expr + term | expr - term | term

term -> term * unary | term / unary | unary

unary -> + factor | - factor

factor - > id | num | (expr)

### 2.2.5

1. 证明：用下面文法生成的所有二进制串的值都能被3整除。（提示：对语法分析树的节点树木使用数学归纳法）

num -> 11 | 1001 | num 0 | num num

2.  上面的文法是否能生成所有能被3整除的二进制串？

#### 解答

1. 证明

符合该文法的二进制串一定是由任意数量的 11，1001 和 0 组成的最左位不为0的序列

该序列的十进制和为：

sum

= Σ<sub>n</sub> (2<sup>1</sup> + 2<sup>0</sup>) * 2 <sup>n</sup> + Σ<sub>m</sub> (2<sup>3</sup> + 2<sup>0</sup>) * 2<sup>m</sup>

= Σ<sub>n</sub> 3 * 2 <sup>n</sup> + Σ<sub>m</sub> 9 * 2<sup>m</sup>

显然是能被3整除的

2. 不是。二进制串10101，数值为21，可被3整除，但无法由文法推导出。

**注：** 还有更一般性的证法么？

# 2.3 节的练习

### 2.3.1

构建一个语法制导翻译方案，该方案把算数表达式从中缀表达式翻译成前缀表达式。

#### 解答

产生式：

    expr -> expr + term
          | expr - term
          | term
    term -> term * factor
          | term / factor
          | factor
    factor -> digit | (expr)

翻译方案：

    expr -> {print("+")} expr + term
          | {print("-")} expr - term
          | term
    term -> {print("*")} term * factor
          | {print("/")} term / factor
          | factor
    factor -> digit {print(digit)}
            | (expr)

### 2.3.2

构建一个语法制导翻译方案，该方案把算数表达式从后缀表达式翻译成中缀表达式。

#### 解答

产生式：

    expr -> expr expr +
          | expr expr -
          | expr expr *
          | expr expr /
          | digit

翻译方案：

    expr -> expr {print("+")} expr +
          | expr {print("-")} expr -
          | {print("(")} expr {print(")*(")} expr {print(")")} *
          | {print("(")} expr {print(")/(")} expr {print(")")} /
          | digit {print(digit)}

#### 疑问

参考答案是：

E -> {print("(")} E {print(op)} E {print(")"}} op | digit {print(digit)}

起初我的答案也是这样，但发现括号冗余比较严重，才改成现在的解答。虽然在多级优先级运算中，其实只能减少最低优先级运算的括号，不过看起来在这样的情况下还是能节约比较多括号的。这个解法正确否？

### 2.3.3

构建一个将整数翻译成罗马数字的语法制导翻译方案。

#### 解答

辅助方法：

    repeat(sign, times) // 将 sign 重复 times 次输出，如 repeat('a',2) = 'aa'

翻译方案：

    num -> thousand hundred ten digit
           { num.roman = thousand.roman || hundred.roman || ten.roman || digit.roman;
             print(num.roman)}
    thousand -> low {thousand.roman = repeat('M', low.v)}
    hundred -> low {hundred.roman = repeat('C', low.v)}
             | 4 {hundred.roman = 'CD'}
             | high {hundred.roman = 'D' || repeat('X', high.v - 5)}
             | 9 {hundred.roman = 'CM'}
    ten -> low {ten.roman = repeat('X', low.v)}
         | 4 {ten.roman = 'XL'}
         | high {ten.roman = 'L' || repeat('X', high.v - 5)}
         | 9 {ten.roman = 'XC'}
    digit -> low {digit.roman = repeat('I', low.v)}
           | 4 {digit.roman = 'IV'}
           | high {digit.roman = 'V' || repeat('I', high.v - 5)}
           | 9 {digit.roman = 'IX'}
    low -> 0 {low.v = 0}
         | 1 {low.v = 1}
         | 2 {low.v = 2}
         | 3 {low.v = 3}
    high -> 5 {high.v = 5}
          | 6 {high.v = 6}
          | 7 {high.v = 7}
          | 8 {high.v = 8}

### 2.3.4

构建一个将罗马数字翻译成整数的语法制导方案。

#### 解答

产生式：

    romanNum -> thousand hundred ten digit
    thousand -> M | MM | MMM | ε
    hundred -> smallHundred | C D | D smallHundred | C M
    smallHundred -> C | CC | CCC | ε
    ten -> smallTen | X L | L smallTen | X C
    smallTen -> X | XX | XXX  | ε
    digit -> smallDigit | I V | V smallDigit | I X
    smallDigit -> I | II | III | ε
翻译方案：
    romanNum -> thousand hundred ten digit {romanNum.v = thousand.v || hundred.v || ten.v || digit.v; print(romanNun.v)}
    thousand -> M {thousand.v = 1}
              | MM {thousand.v = 2}
              | MMM {thousand.v = 3}
              | ε {thousand.v = 0}
    hundred -> smallHundred {hundred.v = smallHundred.v}
             | C D {hundred.v = smallHundred.v}
             | D smallHundred {hundred.v = 5 + smallHundred.v}
             | C M {hundred.v = 9}
    smallHundred -> C {smallHundred.v = 1}
                  | CC {smallHundred.v = 2}
                  | CCC {smallHundred.v = 3}
                  | ε {hundred.v = 0}
    ten -> smallTen {ten.v = smallTen.v}
         | X L  {ten.v = 4}
         | L smallTen  {ten.v = 5 + smallTen.v}
         | X C  {ten.v = 9}
    smallTen -> X {smallTen.v = 1}
              | XX {smallTen.v = 2}
              | XXX {smallTen.v = 3}
              | ε {smallTen.v = 0}
    digit -> smallDigit {digit.v = smallDigit.v}
           | I V  {digit.v = 4}
           | V smallDigit  {digit.v = 5 + smallDigit.v}
           | I X  {digit.v = 9}
     smallDigit -> I {smallDigit.v = 1}
                | II {smallDigit.v = 2}
                | III {smallDigit.v = 3}
                | ε {smallDigit.v = 0}

#### 疑问

参考答案和我的解法有一个显著的区别，如下：

    LowHundreds → ε { LowHundreds.val = 0; }
                | C { LowHundreds.val = 100; }
                | CC { LowHundreds.val = 200; }
                | CCC { LowHundreds.val = 300; }

所以他的最后一步获得翻译后的数字是用的加法：

    RomanNumeral → Thousands Hundreds Tens Ones
                   { RomanNumeral.val = Thousands.val + Hundreds.val + Tens.val + Ones.val;
                   printf(“%d\n”, RomanNumeral.val;) }

看起来我的解法因为使用了更少的0而节约了一些空间，其他也没看出什么坏处，是这样？

### 2.3.5

构建一个将后缀表达式翻译成前缀表达式的语法制导翻译方案。

#### 解答

产生式：

expr -> expr expr op | digit

翻译方案：

expr -> {print(op)} expr expr op | digit {print(digit)}
