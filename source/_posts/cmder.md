---
title: Cmder，一款增强版的 Windows 命令行
date: 2020-04-20 
updated: 2020-04-23 
urlname: Cmder
tags:
  - Shell
  - Windows
  - Cmder
categories: 
  - Shell
  - Windows
  - 教程/Tutorial

copyright: true
permalink: false
top: false
comments: true
password: 
abstract: 🔐咦，这儿有东西被加密了，需要输入密码才能查看~
message: 请输入密码，按[Enter]键确定.
wrong_pass_message: 抱歉, 这个密码看着不太对, 请再试试.
---

**README**
本文介绍 `Cmder` 的安装与使用。
`cmder` 是一个增强型命令行工具，不仅可以使用 `windows` 下的所有命令，更爽的是可以使用 `linux` 的shell命令。
<!---more--->

------

## Cmder

- [官网 official](https://cmder.net/)

- [Github 项目主页](https://github.com/cmderdev/cmder)

**类似程序：**

- [Clink](https://mridgers.github.io/clink/) 600KB 

## Cmder是什么：

`cmder` 是一个增强型命令行工具，不仅可以使用 `windows` 下的所有命令，更爽的是可以使用 `linux` 的 shell 命令。

## mini 和 full 版本差别

full 版自带 `git` ，mini版本只包含 `Linux` 命令

## 安装

1. 解压
2. 添加到系统 `PATH` 环境变量
3. 以 `管理员` 方式运行cmd，输入 `Cmder.exe /REGISTER ALL`
4. 即可在任意文件夹 `右键` 打开了。![效果图](https://cdn.jsdelivr.net/gh/liaozhebin/img@master/imgs/2954885665-59c9e04a5206b_articlex.webp)


## 使用

### 常用快捷键

> Tab自动路径补全
>
> Ctrl+T建立新页签
>
> Ctrl+W关闭页签
>
> Ctrl+Tab切换页签
>
> Alt+F4关闭所有页签
>
> Alt+Shift+1 开启cmd.exe
>
> Alt+Shift+2 开启powershell.exe
>
> Alt+Shift+3 开启powershell.exe(系统管理员权限)
>
> Ctrl+1      快速切换到第1个页签
>
> Ctrl+n快速切换到第n个页签(n值无上限)
>
> Alt+enter切换到全屏状态
>
> Ctr+r历史命令搜索
>
> Win+Alt+P开启工具选项视窗



### 进阶设置
[设置bash作为默认开启的选项](https://segmentfault.com/a/1190000011361877#item-0-8)

[解决中文乱码问题](https://segmentfault.com/a/1190000011361877#item-0-9)

[更改背景](https://segmentfault.com/a/1190000011361877#item-0-11)



## Z.lua 的扩展

### z.lua 介绍

`z.lua` 是一个快速路径切换工具（类似 z.sh / autojump / fasd），兼容 Windows 和所有 Posix Shell 以及 Fish Shell 的同时包含了众多改进，它会跟踪你在 `shell` 下访问过的路径，经过一段简短的学习之后，`z.lua` 会帮你跳转到所有匹配正则关键字的路径里 `Frecent` 值最高的那条路径去，比如：`z foo bar`  可以匹配到  `/foo/bar`  

[Z.lua zh-cn Readme 中文说明](https://github.com/skywind3000/z.lua/blob/master/README.cn.md)

### 正式安装

1. lua 安装  [Click here to download](https://sourceforge.net/projects/luabinaries/files/latest/download)

2. 解压二进制文件，并把路径加入环境变量 

   > 前面已经把 cmder 目录加入环境变量，所以可以直接放入 cmder 文件夹中

3. 重命名 `lua5.3` 为  `lua`

4. 将 z.lua 和 z.cmd 拷贝到 cmder/vendor 目录中。

   > `cd`  到 `cmder/vendor` 目录
   >
   > ```bash
   curl -LO https://raw.githubusercontent.com/skywind3000/z.lua/master/z.cmd https://raw.githubusercontent.com/skywind3000/z.lua/master/z.lua`
	```
5. 将 cmder/vendor 添加到环境变量 `%PATH%` 里面。

6. 保证 lua 命令在 `%PATH%` 环境变量中。

## 参考：
1. [知乎专栏介绍概览](https://zhuanlan.zhihu.com/p/28400466)
2. [Windows Cmder 安装及配置](https://www.jianshu.com/p/bfff2d49f670)
3. [Windows命令行工具cmder配置](https://segmentfault.com/a/1190000011361877)  
4. [Lua在Windows下的安装、配置、运行](https://blog.csdn.net/ChinarCSDN/article/details/78667262)
5. [Z.lua zh-cn Readme 中文说明](https://github.com/skywind3000/z.lua/blob/master/README.cn.md)
