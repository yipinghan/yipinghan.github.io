---
layout:     post
title:      Audio Basic
subtitle:   common concepts
date:       2019-08-10
author:     HYP
header-img: img/post-bg-iWatch.jpg
catalog: true
tags:
    - Audio
    - Acoustic
    - Sound
---



# Introduction

After having got my acoustic master degree, I fould some common were often used in work, so I wrote down some basic info for sharing and marking.<br>

<br>
# Main Body
<br>
## 采样频率
即取样频率, 指每秒钟取得声音样本的次数。采样频率越高,声音的质量也就越好,声音的还原也就越真实，但同时它占的资源比较多。由于人耳的分辨率很有限,太高的频率并不能分辨出来。22050 的采样频率是常用的, 44100已是CD音质, 超过48000或96000的采样对人耳已经没有意义。这和电影的每秒 24 帧图片的道理差不多。<br>
如果是双声道(stereo), 采样就是双份的, 文件也差不多要大一倍.<br>

## 采样位数
即采样值或取样值（就是将采样样本幅度量化）。它是用来衡量声音波动变化的一个参数，也可以说是声卡的分辨率。它的数值越大，分辨率也就越高，所发出声音的能力越强。<br>

每个采样数据记录的是振幅, 采样精度取决于采样位数的大小:<br>
	• 1 字节(也就是8bit) 只能记录 256 个数, 也就是只能将振幅划分成 256 个等级;<br>
	• 2 字节(也就是16bit) 可以细到 65536 个数, 这已是 CD 标准了;<br>
	• 4 字节(也就是32bit) 能把振幅细分到 4294967296 个等级, 实在是没必要了.<br>

## 通道数
即声音的通道的数目。常有单声道和立体声之分，单声道的声音只能使用一个喇叭发声（有的也处理成两个喇叭输出同一个声道的声音），立体声可以使两个喇叭都发声（一般左右声道有分工） ，更能感受到空间效果，当然还有更多的通道数。<br>

## 帧
帧记录了一个声音单元，其长度为样本长度(采样位数)和通道数的乘积<br>

## 周期
音频设备一次处理所需要的帧数，对于音频设备的数据访问以及音频数据的存储，都是以此为单位。<br>

## 交错模式
数字音频信号存储的方式。数据以连续帧的方式存放，即首先记录帧1的左声道样本和右声道样本，再开始帧2的记录...<br>

## 非交错模式
首先记录的是一个周期内所有帧的左声道样本，再记录所有右声道样本。<br>

## 比特率
每秒的传输速率(位速, 也叫比特率)。如705.6kbps 或 705600bps, 其中的 b 是 bit, ps 是每秒的意思，表示每秒705600bit的容量。<br>

以上来自 <https://blog.csdn.net/aoshilang2249/article/details/38469051> <br>

## 信噪比
（Signal-to-noise ratio，缩写为 SNR 或 S/N），也称作信杂比或讯杂比，为有用信号功率(Power of Signal)与噪声功率(Power of Noise)的比。因此为幅度（Amplitude）比的平方：<br>

<a href="https://www.codecogs.com/eqnedit.php?latex=SNR=Psignal/Pnoise=(Asignal/Anoise)^2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?SNR=Psignal/Pnoise=(Asignal/Anoise)^2" title="SNR=Psignal/Pnoise=(Asignal/Anoise)^2" /></a>

它的单位一般使用分贝，其值为十倍对数信号与噪声功率比：<br>
<a href="https://www.codecogs.com/eqnedit.php?latex=SNR(dB)=10\log_{10}(\frac{Psignal}{Pnoise})=20\log_{10}(\frac{Asignal}{Anoise})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?SNR(dB)=10\log_{10}(\frac{Psignal}{Pnoise})=20\log_{10}(\frac{Asignal}{Anoise})" title="SNR(dB)=10\log_{10}(\frac{Psignal}{Pnoise})=20\log_{10}(\frac{Asignal}{Anoise})" /></a>

其中<br>
 为信号功率(Power of Signal)。<br>
 为噪声功率(Power of Noise)。<br>
 为信号幅度(Amplitude of Signal)。<br>
 为噪声幅度(Amplitude of Noise)。<br>

其实信噪比就是信号功率在db单位上的相减，还有一个单位dBm，可看做是用来衡量能量的一个绝对量，以1mW为基准。<br>
 以上来自：<https://blog.csdn.net/xiahouzuoxin/article/details/10949887 ><br>




tips: add formula to git, please refer this :<br>
<https://www.codecogs.com/latex/eqneditor.php><br>
<https://www.jianshu.com/p/c169599726e1><br>

#### Reference
> All content is searched from the Internet, I am trying to pin every original link to cited parts, delete if tort



