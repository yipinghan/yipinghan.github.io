---
layout:     post
title:      Coding sharing summary 1
subtitle:   C/Audio
date:       2019-08-08
author:     HYP
header-img: img/post-bg-universe.jpg
catalog: true
tags:
    - C
    - Audio

---

1.结构体编码的运算符区别<br>
在对结构体进行相应的编码时，时而发现是用点运算符(.)，时而是用箭头运算符(->)<br>
<br>
相同点：两者都是二元操作符，而且右边的操作数都是成员的名称；<br>
不同点：<br>
点运算符(.)的左边操作数是一个结果为结构的表达式；<br>
箭头运算符(->)的左边的操作数是一个指向结构体的指针；<br>
<br>
<br>
例如：访问数据操作如下：<br>
data.age = 24;          // 结构体变量通过点运算符(.)访问<br>
pdata->age = 24;        // 指向结构体的指针通过箭头运算符(->)访问<br>
<br>
来自 <https://blog.csdn.net/ShenYuanLuo/article/details/51146140> <br>
<br>
<br>
2.语音可懂度衡量指标 <br>
STOI (Short-Time Objective Intelligibility, STOI)，将其用于衡量语音增强算法的可懂度性能<br>
在 STOI算法中，同时输入干净的语音 x(n)和经过增强算法重建的干净语音估计 y(n)，STOI 算法会给出一个(0, 1) 范围内的值，STOI 值越大，表示处理后的语音的可懂度越高；<br>
<br>
ST  Short time ~400ms<br>
TF  timefrequency 时频<br>
时频分析的基本思想是：设计时间和频率的联合函数，用它同时描述信号在不同时间和频率的能量密度或强度。时间和频率的这种联合函数简称为时频分布<br>
<br>
来自 <https://baike.baidu.com/item/%E6%97%B6%E9%A2%91%E5%88%86%E6%9E%90/963008?fr=aladdin> <br>
<br>
<br>
3.指针运算<br>
C++ 提供了两种指针运算符，一种是取地址运算符 &，一种是间接寻址运算符 * <br>
指针是一个包含了另一个变量地址的变量，您可以把一个包含了另一个变量地址的变量说成是"指向"另一个变量。<br>
变量可以是任意的数据类型，包括对象、结构或者指针。<br>
<br>
取地址运算符 &<br>
& 是一元运算符，返回操作数的内存地址。<br>
例如，如果 var 是一个整型变量，则 &var 是它的地址。该运算符与其他一元运算符具有相同的优先级，在运算时它是从右向左顺序进行的。<br>
您可以把 & 运算符读作"取地址运算符"，这意味着，&var 读作"var 的地址"。<br>
<br>
间接寻址运算符 * <br>
第二个运算符是间接寻址运算符 * ,它是 & 运算符的补充。* 是一元运算符，返回操作数所指定地址的变量的值。<br>
<br>
来自 <http://www.runoob.com/cplusplus/cpp-pointer-operators.html> <br>
<br>
<br>
4.#define命令<br>
折是C语言中的一个宏定义命令，它用来将一个标识符(宏名)定义为一个字符串，该标识符被称为宏名，被定义的字符串称为替换文本。程序编译之前，编译的时候所有的宏名都会被定义的字符串替换，这便是宏替换。<br>
<br>
理解宏定义的关键在于 “替换”。该命令有两种格式：一种是简单的宏定义，另一种是带参数的宏定义。<br>
(1)简单的宏定义： <br>
#define <宏名><字符串><br>
例： #define PI 3.14 <br>
程序：<br>
```
float pi2 = PI * 2;//pi2 = 6.28
```

(2) 带参数的宏定义 <br>
#define <宏名> (<参数表>) <宏体><br>
例： #define AddOne(x) (x+1) <br>
程序：<br>
```
float pi2 = PI * 2;//pi2 = 6.28
pi2 = AddOne(pi2);// pi2 = 7.28
```
<br>
来自 <https://blog.csdn.net/shuzfan/article/details/52860664> <br>
<br>
<br>
5.运算结果出现 1.#IND, 1.#INF nan, inf 原因<br>
<br>
进行浮点数编程时，如果没有注意，常常会出现输出类似 1.#IND, 1.#INF 或者 nan, inf 之类奇怪的输出。这通常隐含了浮点数操作的异常。<br>
<br>
特殊浮点数的含义<br>
<br>
1.#INF / inf：这个值表示“无穷大 (infinity 的缩写)”，即超出了计算机可以表示的浮点数的最大范围（或者说超过了 double 类型的最大值）。例如，当用 0 除一个整数时便会得到一个1.#INF / inf值；相应的，如果用 0 除一个负整数也会得到 -1.#INF / -inf 值。<br>
<br>
-1.#IND / nan：这个的情况更复杂，一般来说，它们来自于任何未定义结果（非法）的浮点数运算。"IND"是 indeterminate 的缩写，而"nan"是 not a number 的缩写。产生这个值的常见例子有：对负数开平方，对负数取对数，0.0/0.0，0.0* ∞, ∞/∞ 等。<br>
举个例子，如果log()内的值是1.#INF,得到的log值就会是1.#INF。<br>           
<br>
所以简而言之，如果遇到 1.#INF / inf，就检查是否发生了运算结果溢出除零，而遇到 1.#IND / nan，就检查是否发生了非法的运算。<br>
<br>
来自 <http://blog.sina.com.cn/s/blog_5e9e98210101ndgl.html> <br>

<br>
<br>
<br>

#### Reference:

>  Internet searching  - Delete if tort


