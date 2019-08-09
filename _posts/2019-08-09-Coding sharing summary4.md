---
layout:     post
title:      Coding sharing summary4

subtitle:   matlab/python
date:       2019-08-09
author:     HYP
header-img: img/post-bg-debug.png
catalog: true
tags:
    - matlab
    - python
---

# Matlab

1.取整函数有: fix, floor, ceil, round.具体应用方法如下：<br>
<br>
fix：朝零方向取整，如fix(-1.3)=-1; fix(1.3)=1;<br>
floor：顾名思义，就是地板，所以是取比它小的整数，即朝负无穷方向取整<br>
floor(-1.3)=-2; floor(1.3)=1;floor(-1.8)=-2，floor(1.8)=1<br>
<br>
ceil：与floor相反，它的意思是天花板，也就是取比它大的最小整数，即朝正无穷方向取整，如ceil(-1.3)=-1; ceil(1.3)=2;ceil(-1.8)=-1，ceil(1.8)=2<br>
<br>
round：四舍五入到最近的整数，例如：<br>
round(-1.3)=-1;round(-1.52)=-2;round(1.3)=1;round(1.52)=2。<br>
<br>
来自 <https://www.ilovematlab.cn/thread-91895-1-1.html> 




# Python
<br>
1.写入EXCEL表格<br>
经过大量的博客分享查找，最终找到了以下几个说的比较清楚的分享<br>
<https://blog.csdn.net/sinat_28576553/article/details/81275650>
<https://blog.csdn.net/u013250071/article/details/81911434>
<https://blog.csdn.net/kk123a/article/details/49813559>
<https://blog.csdn.net/u013400654/article/details/50284983>
<https://www.cnblogs.com/zhoujie/p/python18.html>
<https://blog.csdn.net/weixin_42122355/article/details/83536142>
<br>
基本可以完成对EXCEL的基本操作<br>
<br>
<br>
2. 加os.system("pause")保持窗口<br>
原因是你双击运行时，程序是按顺序执行的，当执行完最后语句时程序就退出了，给我们的感觉就是有个黑窗口一闪而过，加上os.system("pause")后程序运行结束后会暂停执行，然后等待用户输入再退出。在命令行窗口执行脚本也是可行的，因为程序的输出是到命令行窗口<br>
<br>
<br>
3. Python 打包EXE<br>
打开cmd窗口，需要安装 pyinstaller，pypiwin32<br>
指令：<br>
```
Python -v
Python -m pip install pyinstaller
Python -m pip list
Python -m PyInstaller -w main.py -F -n soundleakageplatform  //项目名中间不能有空格
Python -m PyInstaller -V
Python -m pip list
Python -m pip install pypiwin32
Python -m PyInstaller -w main.py -F -n soundleakageplatform  //第一种生成方式，只有EXE
Python -m PyInstaller -w main.py -n soundleakageplatform  //第二种生成方式，文件夹形式
```
如果出现无法运行脚本的情况，请用下面的语句打包.<br>
```
Python -m PyInstaller -w main.py -F -w -c soundleakageplatform
```
来自<https://blog.csdn.net/h330531987/article/details/85853750><br>
<https://segmentfault.com/a/1190000014781519><br>
<br>
在项目所在的文件夹中打包<br>
只能使用打包成文件夹的形式，注意要把
C:\Python34\Lib\site-packages\PyQt4\plugins的文件夹platforms 复制到打包的文件夹
项目名字\工程名字\dist\soundLeakagePlatform\qt4_plugins 中<br>
这是因为打包的EXE中用了除了python之外的库qt4_plugins，需要打包之后重新引用<br>
<br>
还要把DLL文件复制到：项目名字\工程名字\dist\soundLeakagePlatform 中<br>
<br>
打包后会出现三个文件，一个是build文件夹，一个是dist文件夹，一个是soundLeakagePlatform.spec <br>  
<br>
可执行文件在：项目名字\工程名字\dist\soundLeakagePlatform<br>
如果重新打包，把之前的删了，再重新生成<br>
<br>
<br>
这个方法可以用到很多地方，写好的Py文件也可以直接打包成EXE，提高便携性和使用度<br>
<br>
<br>
<br>
	
#### Reference
	
> Links are from the Internet, delete if tort.
