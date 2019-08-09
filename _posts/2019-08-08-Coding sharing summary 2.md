---
layout:     post
title:      Coding sharing summary 2
subtitle:   C/Audio
date:       2019-08-08
author:     HYP
header-img: img/post-bg-iWatch.jpg
catalog: true
tags:
    - C
    - Audio
---




1.main函数参数argc，argv说明<br>
<br>
C/C++语言中的main函数，经常带有参数argc，argv，如下：<br>
```
int main(int argc, char** argv)
int main(int argc, char* argv[])
```
<br>
这两个参数的作用: <br>
argc 是指命令行输入参数的个数(以空白符分隔) <br>
argv存储了所有的命令行参数<br>
假如你的程序是hello.exe，如果在命令行运行该程序，（首先应该在命令行下用 cd 命令进入到 hello.exe 文件所在目录） 运行命令为：<br>
```
hello.exe Shiqi Yu
```
那么，argc的值是 3，argv[0]是"hello.exe"，argv[1]是"Shiqi"，argv[2]是"Yu<br>
<br>
下面的程序演示argc和argv的使用：<br>
```
#include <stdio.h>

int main(int argc, char ** argv)
{
    int i;
    for (i=0; i < argc; i++)
        printf("Argument %d is %s.\n", i, argv[i]);

    return 0;
}
```
假如上述代码编译为hello.exe，那么运行<br>
```
hello.exe a b c d e
```
会得到<br>
```
Argument 0 is hello.exe.
Argument 1 is a.
Argument 2 is b.
Argument 3 is c.
Argument 4 is d.
Argument 5 is e.
```
运行<br>
```
hello.exe lena.jpg
```
将得到<br>
```
Argument 0 is hello.exe.
Argument 1 is lena.jpg.
```
来自：<http://wiki.opencv.org.cn/index.php/Main%E5%87%BD%E6%95%B0%E5%8F%82%E6%95%B0argc%EF%BC%8Cargv%E8%AF%B4%E6%98%8E>

<br>
<br>
2.转换说明<br>
结果的打印输出
％a 浮点数、十六进制数字和p-记数法（C99）<br>
%A 浮点数、十六进制数字和p-记法（C99）<br>
%c 一个字符<br>
%d 有符号十进制整数<br>
%e 浮点数、e-记数法<br>
%E 浮点数、E-记数法<br>
%f 浮点数、十进制记数法<br>
%g 根据数值不同自动选择％f或％e．<br>
%G 根据数值不同自动选择％f或％e.<br>
%i 有符号十进制数（与％d相同）<br>
%o 无符号八进制整数<br>
%p 指针<br>
%s 字符串<br>
%u 无符号十进制整数<br>
%x 使用十六进制数字0f的无符号十六进制整数<br>
%X 使用十六进制数字0f的无符号十六进制整数<br>
%% 打印一个百分号 使用printf ()函数 printf()的基本形式： printf("格式控制字符串"，变量列表);<br>

输出多个参数往后面写就OK了
来自 <https://zhidao.baidu.com/question/91911205.html> 
<br>
<br>
3.逻辑与，按位与，逻辑或，按位或<br>
逻辑与或是对布尔值进行操作<br>
按位与或是对计算机位操作，属于二进制位运算<br>
逻辑与：全真为真，区分&，&&<br>
逻辑或：有真为真，区分|，||<br>
逻辑非：假才真，！<br>
按位与，按位或，按位非，按照上面规则对每一位进行逻辑运算，1为真0为假<br>
<br>
逻辑运算符用来判断真假，位操作符用来计算<br>

按位与：一个bit位只有0和1两个取值，只有参与&运算的两个位都为1，结果才为1，否则为0
例如：1&1；0&0；1&0，这和逻辑运算符&&非常类似<br>
位运算原理：C中不能直接使用二进制，&两边的操作可以是十进制，八进制，十六进制，他们在内存中最终都是以二进制形式存储，&就是对这些内存中的二进制位进行运算<br>
^按位异或<br>
~取反<br>
<<左移;>>右移<br>
<br>
<br>
<br>
把要转换的变量转换为二进制，再按照规则进行位运算：<br>
1> C语言中的>>=表示：右移后赋值，示例：<br>
```
x=8;   //00000000 00000000 00000000 00001000 十进制8的二进制
x>>=3; //00000000 00000000 00000000 00000001 右移3位，赋值给x，此时x的十进制数为1
```

2> C语言中的<<=表示：左移后赋值，示例：<br>
```
x=8;   //00000000 00000000 00000000 00001000 十进制8的二进制
x<<=3; //00000000 00000000 00000000 01000000 右移3位，赋值给x，此时x的十进制数为1
```

3> C语言中的&=表示：按位与后赋值，示例：<br>
```
x=0x02;   
x&=0x01; //0x00按位与后的结果
```

4> C语言中的^=表示：按位异或后赋值，示例：<br>
```
x=0x02;   
x^=0x01; //0x03等同于0011，按位与异或的结果
```

5> C语言中的|=表示：按位异或后赋值，示例：<br>
```
x=0x02;   
x|=0x01; //0x03等同于0011，按位或的结果
```

4.结构体<br>
为了定义结构体，必须使用struct， struct定义了一个包含多个成员的新数据类型，格式如下：<br>
```
struct tag{
    member-list
    member-list
    member-list
    ...
}variable-list;
```
tag是结构体的标签；<br>
member-list是标准的变量定义，例如int i, float f, 或者其他有效的变量定义；<br>
variable-list结构变量，定义在结构的末尾，最后一个分号之前；<br>
您可以指定一个或多个结构变量，下面是声明Book结构的方式：<br>
```
struct tag{
    char title[50];
    char author[50];
    char subject[100];
    int book_id;
    ...
}book;
```

一般情况下，这三个变量至少要出现2个，示例：<br>
```
//此结构体没有标签
struct {
    int a;
    char b;
    double c
}s1;

//此结构体没有声明变量
struct SIMPLE{
    int a;
    char b;
    double c
};
```
<br>
5. 其他<br>
<br>
1> EPS示浮点相对精度。对双精度数值来说eps表示从 1.0 到下一个最大双精度数的距离。对单精度数值来说eps表示从 1.0 到下一个最大单精度数的距离。<br>

2> C语言中要输出宽字符，可以使用wprintf()，同时要设置本地化，以适应宽字符输出
wprintf(L"%c\n",wc);<br>
来自 <https://zhidao.baidu.com/question/581662751.html> <br>

3>强制转换注意单位,不要改写参数名称,PCM必须16BIT（ASR）<br>

#### Reference:

>  Internet searching  - Delete if tort

