---
layout:     post
title:      Coding sharing summary3
subtitle:   C/Audio
date:       2019-08-09
author:     HYP
header-img: img/post-bg-iWatch.jpg
catalog: true
tags:
    - C
    - Audio
---

> coding issues

# 错误总结
<br>
1. 变量名写错 <br>
<br>
2. C语言容易出现内存泄露：比如加载了wav文件，有两个track，track是柔性数组，但是如果想：track[3]=track[1]，不好这样操作，以为track是在loadwac的时候就读取文件，分配特定好的track，虽然track数组指针可以往后增加，但是前提是内存分配有的情况下，否则就会写入其他的内存区域，导致释放时出错<br>
<br>
3. 释放内存：有时是释放变量，有时是释放buf里面的内容，所以不只是释放指针变量而已，混用会导致内存出错<br>
<br>
4. 如果出现内存泄露不好定位的时候，就用go exit打点，看到底是哪一个位置出现了错误，再去排查。如果不知道波形为什么发生了变化，就每个处理操作之后, 把音频down下来观察变化<br>
<br>
5. 在函数的一开始，都要进行参数检测，例如if (A == NULL || B == NULL) return BadParameter;如果直接加载文件，或者直接处理，可能会带来未知的问题.运行出结果时C没有JAVA的抛出异常，如果有错误结果都要声明，再跳出，最后释放内存<br>
<br>
6. 某种情况是：指针写飞了，但是并不知道哪里写飞了，外部接口调用dll的时候，python报错：access violation writing 0x00000000，就是说写内存的时候错误。虽然C里面运行没有报错，但是可能错误已经存在了，不知道而已<br>
可以使用printf打印出变量的值，并且在每次操作前后打出来，判断变化是否正常<br>
<br>
发现：之前的几次都是有值的，在一次循环里发现，突然变成了0
原因是：输入的wav的track数不一样，如果方法是根据一个tracknum去做另一个track的memove，必然会出现指针飞掉的情况，但是一开始的时候并不知道<br>
<br>
7.python调用DLL时出错：function  not found <br>
可能因为：DLL的位置放的不对，或者引用DLL地址设置的不对<br>

8. python调用DLL时出错：报错，OSError: [WinError 193] %1 不是有效的 Win32 应用程序
还是dll出错了，可能因为：dll-relase的版本和python不匹配<br>
来自<https://blog.csdn.net/weixin_39198406/article/details/84889047>

9. Python 安装pyaudio，报错没有VC++ 2010<br>
这是一个很难搞的问题，究其原因还是VC环境没装好，而到底装哪个也是众说纷纭，指定名字的装了也可能出错，建议按照下面几个地址的方法，或者直接安装VS EXPRESS打包安装VC<br>
https://www.cnblogs.com/yyds/p/7065637.html
https://stackoverflow.com/questions/31161635/microsoft-visual-c-10-0-is-required-unable-to-find-vcvarsall-bat
https://www.devdungeon.com/content/fix-pip-install-unable-find-vcvarsallbat
https://pypi.org/project/PyAudio/#history




#### Reference

> personal experiences, links are from the Internet
