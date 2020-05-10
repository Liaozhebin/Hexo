---
title: Fish，真正开箱即用的 Linux Shell 终端
date: 2020-04-28 
updated: 2020-04-30 
urlname: fish
tags:
  - Shell
  - Linux
  - fish
  - oh-my-fish
categories: 
  - Shell
  - Linux
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


**Readme**

看了之前 `zsh` 的配置教程有些萌萌新可能会觉得有点复杂而头大，简单学习完 zsh 之后发现一款真正 **开箱即用** 的终端 **`Fish`** ，它可以通过包管理器 `apt / yum / dnf` 一键安装，并在不需要任何配置的情况下，达到比传统的 `Bash` 更好用的状态

<!---more--->
 
## 介绍
### 特点：

- **建议**：Fish 会提示你之前写过的命令。当经常输入相同命令时，这样可以提高生产率。
- **基于手册页的补全**：Fish 会根据命令的手册页 `man` 适当的补全参数。
- **语法高亮**：Fish 会高亮显示命令语法以使其在视觉上友好。

### Fish 和 zsh 的对比：

|        | Zsh                |   Fish   |
| ------------------ | ------------------ | ---- |
| **新手友好度** | 需要一定的配置     |   开箱即用   |
| **兼容性** | 能与 Bash 良好兼容 |   与 Bash 兼容性不佳    |
| **运行效率** | 良好       |    效率逊于 Zsh  |
| **适用场景** | 适合长期使用 | 适合短期使用/临时部署服务使用 |



## 安装使用：

### 安装

- Centos:
  - `yum install fish`

- Ubuntu:
  - `apt install fish`

### 使用

#### 启动 Fish

由于 **兼容性问题**，不太推荐大家使用 `chsh -s /usr/bin/fish` 命令把 `fish` 设置为默认 shell 程序，而采用运行 `fish` 命令方式在当前终端会话中启动，毕竟还是用 `bash` 语法的多 🙃 。

#### 历史命令补全

当键入历史命令时，会有灰色文本显示之前编写的命令，只需按 `CTRL+F` 或 `右方向键` 即可自动补全。

#### Tab 补全

通过输入连接号（`–`）然后使用 `TAB` 键，`fish` 会根据对应命令的帮助手册 `man` 获取参数建议：

- 按一次 `TAB`，它将显示前几个建议（或所有建议，如果只有少量参数可用）
- 按二次  `TAB`，它将显示所有建议。
- 连续三次按 `TAB`，它将切换到交互模式，你可以使用方向键选择一个参数。



## Oh My Fish 让 fish 更强大

[官方文档 Zh-cn 中文](https://github.com/oh-my-fish/oh-my-fish/blob/master/docs/zh-CN/README.md)

跟 `zsh` 的 `oh-my-zsh` 类似，使用了一两天后，发现 `fish` 居然也有一款社区开源的**配置框架**文件 `Oh My Fish ` (简称 `omf` ) 

它让每一个使用者可以轻松安装插件或随心所欲更换 Shell 外观样式，并且和 `fish` 一样近乎开箱即用，让你**如鱼得水**。

使用 `omf` 命令，你可以根据你的想法，很容易地安装主题来丰富外观 和 安装插件来增强你的 Fish shell。

### 安装

#### 安装 Oh My Fish 

- curl 方式
  - `curl -L https://get.oh-my.fish | fish`

> 完成后你会发现 `fish shell` 已经变得更漂亮，可以直接食用，也可以选择跟着后面的步骤让它变得 **更强大**

#### 卸载 Oh My Fish

- `omf destroy`

### omf 命令使用

`omf` 可以简单的理解为一个类似于 `apt/yum` 这样的包管理器命令吧

#### 安装主题和插件

##### 查看可用和已安装的主题：

- `omf theme`

  > [可以点击进入官方文档预览所有主题](https://link.zhihu.com/?target=https%3A//github.com/oh-my-fish/oh-my-fish/blob/master/docs/Themes.md)

##### 安装一个 主题 or 插件：

- `omf install [theme-name or plugin-name]`

- `omf install  vi-mode  z extract bira weather`

  > 插件可在 [`omf`  主仓库](https://github.com/oh-my-fish) 中寻找

##### 选择主题

安装了多个主题后需要切换另一个主题

- `omf theme [theme-name]`

#### 安装 bobthefish 主题

[bothefish theme 项目主页 900+ star](https://github.com/oh-my-fish/theme-bobthefish)

这是一个大致基于 [oh-my-zsh agnoster](https://gist.github.com/agnoster/3712874) 的主题

##### 安装字体依赖包 

<details><summary>因博主安装字体后不知如何应用字体，所以折叠跳过</summary> 

字体依赖包 [Powerline fonts](https://github.com/powerline/fonts)

- debian、ubuntu：`apt-get install fonts-powerline`

- other systems：

   ```bash
    git clone https://github.com/powerline/fonts.git --depth=1
    cd fonts && ./install.sh
    cd .. && rm -rf fonts
   ```

</details>

##### 安装主题：

- `omf install bobthefish`

##### 更换配色方案

- `set -g theme_color_scheme dark`  选用默认`dark`配色
- **可选配色：**
  - `dark`. The default bobthefish theme.
  - `light`. A lighter version of the default theme.
  - `solarized` (or `solarized-dark`), `solarized-light`. Dark and light variants of Solarized.
  - `base16` (or `base16-dark`), `base16-light`. Dark and light variants of the default Base16 theme.
  - `zenburn`. An adaptation of Zenburn.
  - `gruvbox`. An adaptation of gruvbox.
  - `dracula`. An adaptation of dracula.
  - `nord`. An adaptation of nord.

#### 包管理

##### 列出已安装的主题和插件：

- `omf list`

	> 所有官方和社区支持的包（包括插件和主题）都托管在 [`omf` 主仓库](https://github.com/oh-my-fish) 中。在主仓库里，你可以看到大量的仓库，其中包含大量的插件和主题。

##### 寻找包

- `omf search [theme-name or plugin-name]`    寻找主题 or 插件 

- **限制寻找范围**
     - `-t`: 只搜索主题
          `-p`: 只搜索插件

##### 更新包

- `omf update`  更新所有包
- `omf update omf` 更新 omf 包
- `omf update [name]` 更新指定 name 包








## 注解与参考
### 参考
> 前人栽树后人乘凉...

[**bobthefish** ：A Powerline-style, Git-aware  fish theme optimized for awesome.](https://github.com/oh-my-fish/theme-bobthefish)

[Fish：一个友好的交互式 Shell | Linux 中国](https://zhuanlan.zhihu.com/p/124293772)

[Oh My Fish! 让你的 Shell 漂亮起来](https://zhuanlan.zhihu.com/p/35448750)