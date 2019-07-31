---
layout:     post
title:      The first post
subtitle:   Hello World, hello you
date:       2019-07-31
author:     Hyp
header-img: img/post-bg-hacker.jpg
catalog: true
tags:
    - iOS
    - Xcode
    - shell
---


# 前言
> 利用xcode的命令行工具 `xcdeobulid` 进行项目的编译打包，生成ipa包

现在网上的自动打包教程几乎都还是`xcodebuild + xcrun`的方式先生成`.app`包 再生成`.ipa`包,结果弄了一整天硬是没成功~

后来发现`PackageApplication is deprecated`，悲剧。然后手动压缩的 `.ipa`包因为签名问题无法装到手机上。

后来用了`archive + -exportArchive`终于可以了~

## 查看项目详情

xcodebuild 的使用可以用 `man xcodebuild`查看。

我只介绍关键的用法

查看项目详情

	xcodebuild -list

## 打包项目 archive -> ipa
首先需要创建一个`AdHocExportOptions.plist`文件

添加两个Key-Value

- merhod : ad-hoc
- compileBitcode : NO

或者直接复制






> It was posted here the first time [HYP Blog](https://yipinghan.github.io)
> Author: HYP
> If you wanna re-post, please keep the original link.

