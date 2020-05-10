---
title: RDPWrap，Windows 多用户远程连接补丁
date: 2020-05-08 
updated: 2020-05-09 
urlname: RDPWrap_fix
tags:
  - Windows
  - 远程连接
categories: 
  - Windows
  - 教程/Tutorial
  - 笔记/Notes

copyright: true
permalink: false
top: false
comments: true
password: 
abstract: 🔐咦，这儿有东西被加密了，需要输入密码才能查看~
message: 请输入密码，按[Enter]键确定.
wrong_pass_message: 抱歉, 这个密码看着不太对, 请再试试.
---

## 补丁作用：

正常情况下 **家庭版 Windows** 是没有远程连接的功能的，而比家庭版更高级的 **专业版/企业版** 虽然有远程连接支持，但是相比于 **Server 服务器版** ，还是限制了只允许一个用户登录使用电脑,

> 比如：名称 `B` 的用户远程连接进来你的电脑，本地使用着电脑的（你）`A` 用户必须退出登录，`B` 才可连接上。

而这个补丁的作用就是让 **非 Server 服务器版 Windows**  能够拥有一个完整版的远程功能（支持多用户远程 **同时** 连接）

<!---more--->

## 补丁工具：

[Github 项目地址](https://github.com/stascorp/rdpwrap)

一位大神在 Github 发布了其制作的补丁工具，支持 [Windows 10](https://www.iplaysoft.com/windows10.html)、Windows 7、Windows 8/8.1、Vista 系统，可以方便的帮你补上这个功能。

### 修补过程

1. 在 [release](https://github.com/stascorp/rdpwrap/releases) 页面下载最新版 `zip` 解压至桌面

   - `写博文时最新版是 1.6.2`

2. 右键以管理员身份运行 `install.bat`，运行完毕后可以看到 `Successfully installed.`

3. 右键以管理员身份运行 `update.bat`。

4. 打开 `RDPConf.exe` 检测是否可用

   - 正常情况下 `Diagnostcs 检查结果` 应该长这样，**4** 个绿色状态，说明安装成功，可以正常使用了。

     > ![](https://cdn.jsdelivr.net/gh/liaozhebin/img@master/imgs/Snipaste_2020-05-07_21-46-57.png)

   - 如果出现 `not listening`  和 `[not supported] ` ，说明安装的版本不支持当前的 windows 版本，我们需要手动对 `C:\Program Files\RDP Wrapper` 目录里面的 `rdpwrap.ini文件` 进行升级。

     > ![](https://cdn.jsdelivr.net/gh/liaozhebin/img@master/imgs/N_support.png)
     >
     > 1. `CMD` 中运行 `winver` 命令，确定当前 windows 版本。
     >
     > 2. 然后在 [Github issue](https://github.com/stascorp/rdpwrap/issues) 里面找到别人发布包含你这个版本的 `rdpwrap.ini` 替换 `C:\Program Files\RDP Wrapper` 目录里面的 `rdpwrap.ini`文件。
     >
     >    > 如果替换时显示文件被占用，我们可以用 CMD 命令`net stop "Remote Desktop Services" ` 暂停远程桌面服务对文件的占用后再进行覆盖替换，替换成功后运行 CMD 命令 `net start "Remote Desktop Services"` 重新开启服务。
     >
     > 3. 这时，再次打开  `RDPConf.exe` ，应该就能看到 **4** 个绿色状态的检查结果了，说明安装成功，可以正常使用了。

5.  Enjoy it. 

#### 我使用的 ini 文件

下图是我 `Windows ` 的版本信息，使用的 `rdpwrap.ini` 文件来自于 [这里](https://raw.githubusercontent.com/affinityv/INI-RDPWRAP/master/rdpwrap.ini)

> ![](https://cdn.jsdelivr.net/gh/liaozhebin/img@master/imgs/winver.png)



## 注解与参考

### 参考

> 前人栽树后人乘凉...

[远程桌面会话多开 RDP WRAPPER 使用方法](https://blog.csdn.net/ljy1221/article/details/103731212)

[我在这个 Issue 中找到了我对应版本的 rdpwrap.ini ](https://github.com/stascorp/rdpwrap/issues/1073)

### 注解

[^1]: [Powerline 字体主页](https://github.com/powerline/fonts)
[^2]: [nerd-font 字体主页](https://github.com/ryanoasis/nerd-fonts)