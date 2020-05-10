---
title: Scoop，一款Windows的包管理器
date: 2020-05-02 
updated: 2020-05-04 
urlname: Scoop
tags:
  - Shell
  - Windows
  - Scoop
categories: 
  - Shell
  - Windows
  - 教程/Tutorial
  - 包管理器

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
本文介绍 `Scoop` 的安装与使用，Scoop 是一款 Windows 下的软件包管理器，类似于Linux下的`apt / yum / dnf`，通过命令可以很方便的安装你想到的软件到指定路径。
<!---more--->

------


## 引言

> 偶然发现一个挺适合小白了解入门与掌握使用的视频，放在最前帮助大家理解，此文就作为文字版吧。
>
> <iframe src="//player.bilibili.com/player.html?aid=75251352&bvid=BV1BE411Y7Go&cid=128723180&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true" height="400px"> </iframe>



## 介绍：

- [[官网]](https://scoop.sh)
- [[Github]](https://github.com/lukesampson/scoop)
- [[Github Project Wiki]](https://github.com/lukesampson/scoop/wiki)

`scoop` 擅长于安装 **便携性程序 portable apps**，例如压缩文件提取后即可独立运行、不会更改注册表、不会将文件放置于程序目录之外的这类软件
### 特别提示：

由于 `scoop` 仓库中的软件源大多数都来自于 `Github` 等国外网站，所以个人只推荐在有 `国际网络加速` 的环境下使用这个包管理器。

要不然会很容易出现各种错误，比如：显示软件已安装、命令行假卡死状态等。
### 类似程序：
[Chocolaty](http://chocolatey.org/)
## 安装

```powershell
# 将执行策略改为允许本地未知无签名的脚本
Set-ExecutionPolicy RemoteSigned -scope CurrentUser
# 下载并执行脚本
iwr -useb get.scoop.sh | iex
```

### 安装路径

#### 默认路径

`scoop` 和 `下载的软件包` 默认安装路径为：

```
C:\Users\<user>\scoop
```

不介意安装到 `C盘` 可以跳过下面的自定义安装路径了。

#### 自定义安装路径

> 可以自己去 `环境变量PATH` 中定义 scoop 安装路径，使用以下命令后，也会自动添加路径 `PATH` 到环境变量中。
> `User` 对应于 当前用户变量
> `Machine` 对应于 系统变量

```powershell
# 设置 scoop和非全局应用 安装路径为 D:\Applications\Scoop
$env:SCOOP='D:\Applications\Scoop'
[environment]::setEnvironmentVariable('SCOOP',$env:SCOOP,'User')
# 安装 scoop
iwr -useb get.scoop.sh | iex

# 全局安装路径修改
$env:SCOOP_GLOBAL='D:\Applications\GlobalScoopApps'
[environment]::setEnvironmentVariable('SCOOP_GLOBAL',$env:SCOOP_GLOBAL,'Machine')
scoop install -g <app_name>
```



## 常用指令

查看帮助：

```powershell
scoop 或者 scoop help		#查看帮助
```



搜索软件/查看软件信息

```powershell
# 搜索安卓相关软件
scoop search android

# 查看 Android Studio 的软件信息
scoop info android-studio    # 可以查看到版本号和软件描述核对软件信息

# 查看软件的依赖：
scoop depends v2rayn

# 查看软件位置
scoop which <app_name>
```



安装/卸载/更新/已安装 软件：

```powershell
# 安装
scoop install <softeware> # 添加 --global 参数给所有用户安装，添加sudo使用管理员权限

# 卸载
scoop uninstall scoop #卸载 scoop 自己, --purge 参数清除持久化数据 persit, 卸载后对应软件的下载 cache 仍然保留

# 更新
scoop update curl 	#更新指定的 curl
scoop update *      # 更新所有软件

# 查看已安装的的软件
scoop list adopt # 列出已安装名字中带有 adopt 的软件，不填写则列出所有已安装软件
scoop export
```



软件仓库管理：

```powershell
scoop bucket known   #查看已知仓库源
scoop bucket add extras  #添加 extras 仓库
```



软件管理/清除缓存：

```
# 删除软件的老版本
scoop cleanup

#清理下载缓存；软件在下载后会保留安装包，所以需要清理
scoop cache #查看缓存
scoop cache clear #删除缓存

# 切换软件版本
scoop reset python27

# 禁用某软件更新
scoop hold/unhold <app_name> 
```



配置scoop：

```powershell
scoop config proxy localhost:10800   # 配置 scoop 使用本地代理，似乎只支持HTTP代理
scoop config rm proxy   # 删除已经配置的代理。
scoop config aria2-max-connection-per-server  # 配置 aria2 程序的单任务最大连接数
```





## 添加软件源

```powershell
# 添加软件源功能依赖于 git，请确保电脑中已经安装 git 并且配置好了环境变量（也可以使用 scoop 安装 git）
# 列出官方已知软件源
scoop bucket known
# 添加额外软件源，默认只有main软件源，主要是 command-line 的开发工具
scoop bucket add extras # 推荐添加这个软件源，大部分软件都再这个源里
# 添加官方未知软件源
scoop bucket add name gitrepo # name 处填写自定义的名字，gitrepo 处填写 git 地址
```



## 问题记录

1. Q: 安装 scoop 的过程中网络连接错误，重新执行安装指令显示已经安装

   A: 删除 `%USERPROFILE%\scoop` 这个文件夹。

2. Q: 使用 scoop 安装软件时下载失败，重新执行安装指令显示已安装

   A: 先执行 scoop uninstall <软件名>，再次执行安装指令即可

3. Q: 如何安装软件指定版本

   A: `scoop install app@version`。例如，`scoop install curl@7.56.1`。仅当旧版本仍可在线下载时，此功能才可用。



## 与包管理工具 `Chocolatey` 的比对

`scoop` 拥有如官方所述的绿色化，bucket 里的软件不会更改用户注册表，不会在用户定义目录之外的地方创建文件（除了 nonportable bucket 的里软件），除了全局安装不需要任何管理员权限。
而 **绿色化带来的弊端** 就是不会再系统中注册为系统服务，不会自动添加到右键菜单。

**相比之下：**

巧克力安装任何软件都需要管理员权限，同时安装目录为目标软件的默认目录，也就是一般情况下，软件都安装到 `C盘` 去了，虽然可以使用 `installdir` 指定安装路径，但是需要收费版才支持。

这样对于一般用户来说似乎就只适合用 `chocolatey` 安装部分软件了。

> 深度使用的和默认不可自定义安装目录的软件
> Portable 便携式软件默认安装到 chocolatey 目录
> 参考：[定制chocolatey安装路径]([https://github.com/chennnnny/good-use-software/wiki/%E5%AE%9A%E5%88%B6chocolatey%E5%AE%89%E8%A3%85%E8%B7%AF%E5%BE%84](https://github.com/chennnnny/good-use-software/wiki/定制chocolatey安装路径))

**【软件使用命令记录】**


```powershell
# Chocolatey 安装路径修改
$env:ChocolateyInstall='D:\Applications\Chocolatey'
[environment]::setEnvironmentVariable('ChocolateyInstall',$env:ChocolateyInstall,'Machine')

# 软件的搜索安装卸载基本跟 scoop 类似
# 安装软件
choco install chocolateygui spotify qbittorent f.lux telegram handbrake
# 可选的安装包
option:choco install teamviewer.host
```

【Chocolatey 的相关链接】

> [使用 Powershell 安装 Chocolatey](https://github.com/chocolatey/choco/wiki/Installation#install-with-powershellexe)
> [chocaolatey 支持的软件列表](https://chocolatey.org/packages)



## 附录：scoop 文件夹结构

- scoop
  - apps # 软件文件夹，所有非全局安装的软件都在这
    
    > appname/current # 当前软件版本对应的文件夹的软链接，如果你对某个软件设置调用该文件夹下的软件（例如 maven 环境设为 current 目录，那么这个指向的软件永远都会是最新版本）
    
  - buckets # 软件源文件夹
  
    > 所有软件的下载地址等元数据都保存在这里，内部文件夹都是由 git 形成的，因此也可以采用 git pull 来更新源。
  
  - cache # 软件安装包所在位置
  
    > 如果遇到软件下载缓慢的情况，也可以用其他工具下载对应软件，然后修改文件名放置到这个目录下进行安装。
  
  - [persist](https://github.com/lukesampson/scoop/wiki/Persistent-data#definition) # 永久配置文件夹
  
    > **大部分的软件的配置都会存到这个目录下**，以保证软件最新版用的都是原来的配置。
  
  - shims # 软件二进制的超链接
  
    > 基本所有的命令行工具都会在这个文件夹内建立一个超链接，目的是为了防止环境变量 PATH 受到过多污染。





## 附录：Scoop 的软件列表

以下是各个扩展仓库的主页，进入可以查看支持的软件，来决定是否启用 `bucket` 

[The following buckets are known to scoop:](https://github.com/lukesampson/scoop#known-application-buckets)

- [main](https://github.com/ScoopInstaller/Main) - Default bucket for the most common (mostly CLI)      apps
- [extras](https://github.com/lukesampson/scoop-extras) - Apps that don't fit the main bucket's [criteria](https://github.com/lukesampson/scoop/wiki/Criteria-for-including-apps-in-the-main-bucket)
- [games](https://github.com/Calinou/scoop-games) - Open source/freeware games and game-related      tools
- [nerd-fonts](https://github.com/matthewjberger/scoop-nerd-fonts) - Nerd Fonts
- [nirsoft](https://github.com/kodybrown/scoop-nirsoft) - A subset of the [250](https://github.com/rasa/scoop-directory/blob/master/by-score.md#MCOfficer_scoop-nirsoft) [Nirsoft](https://nirsoft.net/) apps
- [java](https://github.com/ScoopInstaller/Java) - Installers for Oracle Java, OpenJDK, Zulu,      ojdkbuild, AdoptOpenJDK, Amazon Corretto, BellSoft Liberica &      SapMachine
- [jetbrains](https://github.com/Ash258/Scoop-JetBrains) - Installers for all JetBrains utilities and IDEs
- [nonportable](https://github.com/TheRandomLabs/scoop-nonportable) - Non-portable apps (may require UAC)
- [php](https://github.com/ScoopInstaller/PHP) - Installers for most versions of PHP
- [versions](https://github.com/ScoopInstaller/Versions) - Alternative versions of apps found in other      buckets

### 我通过 scoop 安装的软件：

#### 启用的仓库：

```powershell
scoop bucket add extras nerd-fonts nonportable
```

#### 一键安装以下软件：

```powershell
scoop install 7zip git rufus mpc-be typora listary sumatrapdf spotify
```


#### 软件详情：
##### 压缩 && 解压缩工具 - 7zip

[官网](https://www.7-zip.org/)

```powershell
scoop install 7zip
```


##### 快速搜索工具 - Everything

[官网](https://www.voidtools.com/)

```powershell
scoop install everything
```

##### 快速启动工具 - Wox && Listary

[wox](http://www.wox.one/) [listary](https://www.listary.com/)

```powershell
scoop install wox
scoop install listary
```

##### 截图工具 - snipaste

```powershell
scoop install snipaste
```

##### 编辑工具 - VSCode && sublime

[vscode](https://code.visualstudio.com/) [sublime](https://www.sublimetext.com/) notepad++

```powershell
scoop install vscode
scoop install sublime-text
scoop install notepadplusplus
```

##### Markdown 编辑器 - Typora

[typora](https://typora.io/) [mermaid](https://mermaidjs.github.io/)

```powershell
scoop install typora
```

##### PDF 

```powershell
scoop install sumatrapdf
```



##### 卸载工具 - Geek uninstaller

```powershell
scoop install geekuninstaller
```

##### 视频播放器 - mpc-be - Potplayer

```powrshell
scoop install mpc-be
scoop install potplayer
```

##### 视频录制 / 直播工具 - OBS-studio

[官网](https://obsproject.com/)

```powershell
scoop install obs-studio
```
##### 屏幕显示按钮工具 - carnac

[Github](https://github.com/Code52/carnac)

```powershell
scoop install carnac
```

**设置修改：**修改勾选上 `Appearance` 中的 `show space as` 和 `show application icon` 选项



##### 刻录工具 - Rufus

[官网](http://rufus.ie/)

```powershell
scoop install rufus
```

##### 快速预览工具 - QuickLook

微软应用商店获取 uwp 版本，scoop 可以获取常规版本

```powershell
scoop install quicklook
```


##### Unix 工具集 - busybox / cygwin / msys2

```powershell
scoop install busybox
```
##### 数据库工具 - Heidisql

[heidisql](https://www.heidisql.com/)

```powershell
scoop install heidisql
```

##### 终端工具 - posh-git && oh-my-posh && windows terminal

[posh-git](https://github.com/dahlbyk/posh-git) [oh-my-posh](https://github.com/JanDeDobbeleer/oh-my-posh) [terminal](https://www.microsoft.com/en-us/p/windows-terminal-preview/9n0dx20hk701) [powerline](https://github.com/powerline/fonts)

```powershell
# Windows Terminal 请从微软商店下载
scoop install posh-git oh-my-posh

# 打开配置
notepad $Profile

# 启用 posh-git 和 oh-my-posh，在打开的配置文件里写入下面这些内容
Import-Module posh-git
Import-Module oh-my-posh

# 设置主题
Set-Theme Paradox # 主题可以去 oh-my-posh 的 github 页面找自己喜欢的，部分主题需要使用 powerline 字体，powerline 字体可以通过在 scoop 里增加 nerd-fonts bucket 安装 nerd-fonts 来支持

# 安装 powerline 字体
scoop bucket add nerd-fonts
scoop install Hack-NF # 比如说使用有 powerline 补丁的 hack 字体，powershell 原生的 terminal 不支持这些字体，所以请安装其他的终端模拟器来使用，比如 windows terminal
```

**我的 windows terminal 配置**

```json
// This file was initially generated by Windows Terminal 0.11.1121.0
// It should still be usable in newer versions, but newer versions might have additional
// settings, help text, or changes that you will not see unless you clear this file
// and let us generate a new one for you.

// To view the default settings, hold "alt" while clicking on the "Settings" button.
// 查看默认设置，请按住 Alt 键来点击设置即可查看。
// For documentation on these settings, see: https://aka.ms/terminal-documentation


{
    "$schema": "https://aka.ms/terminal-profiles-schema",

    // "defaultProfile": "{61c54bbd-c2c6-5271-96e7-009a87ff44bf}", //Powershell
    "defaultProfile": "{0caa0dad-35be-5f56-a8ff-afceeeaa6101}",

    // You can add more global application settings here.
    // To learn more about global settings, visit https://aka.ms/terminal-global-settings

    // If enabled, selections are automatically copied to your clipboard.
    "copyOnSelect": false,

    // If enabled, formatted data is also copied to your clipboard
    "copyFormatting": false,

    // A profile specifies a command to execute paired with information about how it should look and feel.
    // Each one of them will appear in the 'New Tab' dropdown,
    //   and can be invoked from the commandline with `wt.exe -p xxx`
    // To learn more about profiles, visit https://aka.ms/terminal-profile-settings
    "profiles":
    {
        "defaults":
        {
            // Put settings here that you want to apply to all profiles.
            // 全局 profiles 设定放在这里
            //"backgroundImage" : "https://cdn.jsdelivr.net/gh/liaozhebin/images@master/SimpTab-20161112080119-Bing.com Image-European.jpg",
            "backgroundImage" : "https://gitee.com/liaozhebin/images/raw/master/img/1008240.jpg", //雪莉
            "backgroundImageOpacity" : 0.5,
            "colorScheme": "Dark",
            "useAcrylic": true,
            "acrylicOpacity": 1,
            "fontFace": "Cascadia Code",
            "fontSize": 12,
            "cursorShape": "emptyBox"
        },
        "list":
        [
            {
                // Make changes here to the powershell.exe profile.
                "guid": "{61c54bbd-c2c6-5271-96e7-009a87ff44bf}",
                "name": "Windows PowerShell",
                "commandline": "powershell.exe",
                "hidden": false
                
            },
            {
                // Make changes here to the cmd.exe profile.
                "guid": "{0caa0dad-35be-5f56-a8ff-afceeeaa6101}",
                "name": "命令提示符",
                "commandline": "cmd.exe",
                "hidden": false
            },
            {
                "guid": "{b453ae62-4e3d-5e58-b989-0a998ec441b8}",
                "hidden": false,
                "name": "Azure Cloud Shell",
                "source": "Windows.Terminal.Azure"

            }
        ]
    },

    // Add custom color schemes to this array.
    // To learn more about color schemes, visit https://aka.ms/terminal-color-schemes
                "schemes": [
            {
              "name": "Dark",
              "black": "#ffffff",
              "red": "#ff5555",
              "green": "#55ff55",
              "yellow": "#c19c00",
              "blue": "#5555ff",
              "purple": "#ff55ff",
              "cyan": "#55ffff",
              "white": "#bbbbbb",
              "brightBlack": "#555555",
              "brightRed": "#ff5555",
              "brightGreen": "#55ff55",
              "brightYellow": "#c19c00",
              "brightBlue": "#5555ff",
              "brightPurple": "#ff55ff",
              "brightCyan": "#55ffff",
              "brightWhite": "#ffffff",
              "background": "#000000",
              "foreground": "#24ff24"
            }

                ],


    // Add custom keybindings to this array.
    // To unbind a key combination from your defaults.json, set the command to "unbound".
    // To learn more about keybindings, visit https://aka.ms/terminal-keybindings
    "keybindings":
    [
        // Copy and paste are bound to Ctrl+Shift+C and Ctrl+Shift+V in your defaults.json.
        // These two lines additionally bind them to Ctrl+C and Ctrl+V.
        // To learn more about selection, visit https://aka.ms/terminal-selection
        // 复制和粘贴
        { "command": {"action": "copy", "singleLine": false }, "keys": "ctrl+c" },
        { "command": "paste", "keys": "ctrl+v" },

        // Press Ctrl+Shift+F to open the search box  
        // 打开搜索框
        { "command": "find", "keys": "ctrl+shift+f" },

        // Press Alt+Shift+D to open a new pane.
        // - "split": "auto" makes this pane open in the direction that provides the most surface area.
        // - "splitMode": "duplicate" makes the new pane use the focused pane's profile.
        // To learn more about panes, visit https://aka.ms/terminal-panes
        // 打开一个新面板并适应化分屏
        { "command": { "action": "splitPane", "split": "auto", "splitMode": "duplicate" }, "keys": "alt+shift+d" },

        // 关闭窗口：
        {"keys": ["ctrl+d"],"command": "closeTab"}
    ]
}
```





## 注解与参考

### 参考

> 前人栽树后人乘凉...

[让 Windows 更好用—包管理工具 scoop 使用攻略/踩坑攻略](https://www.bilibili.com/video/BV1BE411Y7Go/)

[官方Wiki：scoop 与 chocolatey 的对比](https://github.com/lukesampson/scoop/wiki/Chocolatey-Comparison)

[official-wiki: 持久化数据](https://github.com/lukesampson/scoop/wiki/Persistent-data#definition)

### 注解

[^1]: [Powerline 字体主页](https://github.com/powerline/fonts)
[^2]: [nerd-font 字体主页](
