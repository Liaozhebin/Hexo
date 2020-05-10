---
title: antigen，Zsh 的包管理器
date: 2020-05-01 
updated: 2020-05-03 
urlname: Ranger
tags:
  - Shell
  - Linux
  - Zsh
  - oh-my-zsh
  - antigen
  - 包管理器
categories: 
  - Shell
  - Linux
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


**Readme**

觉得前面的 `zsh` 安装太复杂？ 试试它的包管理器 `antigen` 吧，一个能够让你 **更快更轻松** 部署好用 `Shell` 环境的工具。

[Github 项目主页](https://github.com/zsh-users/antigen)
<!---more--->
 


## 安装：

### 安装环境：

```bash
apt install -y zsh git wget curl fzf lua5.3
cp /usr/bin/lua5.3 /usr/bin/lua
```

### 安装 antigen

```bash
curl -L git.io/antigen >.antigen.zsh
```

这个 `antigen` 其实只是一个 `zsh` 脚本而已，所以安装起来非常简单，直接下载为 `HOME` 目录下的隐藏文件即可。之后更新的时候也很简单，重复运行该命令，覆盖旧脚本的即可。

### 编辑 .zshrc 配置文件

这里的配置文件内容其实也算是 `antigen` 的配置文件，是设置如何让 `antigen` 去初始化 `zsh` 。

1. 打开 .zshrc 文件：
   
   - `cd $HOME && vim ./.zshrc`
   
2. 导入以下文件内容

   > 本配置默认启用 `powerlevel10k` 主题，要求 `zsh` 版本 > `5.1`  。
   >
   > 如版本不符，推荐更改为内置主题 `bira`

```bash
# 导入下载好的 .antigen.zsh 文件
source $HOME/.antigen.zsh
    
# Load the oh-my-zsh's library 使用oh-my-zsh
antigen use oh-my-zsh

# ----------------主题theme---------------
# Load the theme
# Internal theme
	#antigen theme bira	
	
#Extra themes:
	antigen theme romkatv/powerlevel10k

# --------------Plugin插件----------------
# antigen bundle 
# oh-my-zsh的默认插件包 Bundles from the default repo (robbyrussell's oh-my-zsh) 
    antigen bundle git
    antigen bundle fzf
    antigen bundle history
    antigen bundle history-substring-search
    antigen bundle zsh-interactive-cd
    antigen bundle vi-mode
    antigen bundle extract 
    antigen bundle docker
    antigen bundle docker-compose
    antigen bundle alias-finder
# ---------
# Load Extra Plugins
	# z.lua 快速路径跳转插件
	antigen bundle skywind3000/z.lua
	
    # Syntax highlighting bundle.
    antigen bundle zsh-users/zsh-syntax-highlighting

    # Fish一样的命令提示插件 Fish-like auto suggestions 
    antigen bundle zsh-users/zsh-autosuggestions

    # Extra zsh completions
    # antigen bundle zsh-users/zsh-completions
    
    


# Tell antigen that you're done
antigen apply


```

### 应用配置

关闭当前 `Shell` 终端，重新连接打开，键入命令 `zsh` 即可进入 `zsh` 终端。

至此，你已经可以愉快的享用 `zsh` 为你带来的高效了。

如果需要把 `zsh` 设置为默认 `Shell`，则使用命令 `chsh -s $(which zsh)` 来切换。





## 使用 powerlevel10k 主题

为了能够更好的使用主题特性，我们需要安装增强版字体依赖。

<details><summary>因博主安装字体后不知如何应用字体，所以折叠</summary> 

- **安装字体依赖** [^1][^2]

> 似乎安装完成后需要在终端设置中，选中该字体。

```bash
apt install fontconfig fonts-powerline
```

</details>



## 使用我的配置文件

如果喜欢我的上面的配置方案或者懒得设置的话，还可以直接使用我的配置文件。直接在 `HOME` 目录中执行下面几条命令，下载 `.zshrc` 和 `.p10k.zsh` 两个文件，就可以使用上我的配置方案了。

```bash
cd $HOME
curl -L git.io/antigen >.antigen.zsh
curl -L https://raw.githubusercontent.com/Liaozhebin/files/master/.antigen > .zshrc
curl -L https://raw.githubusercontent.com/Liaozhebin/files/master/.p10k.zsh > .p10k.zsh
```

下载完成之后，重新登录 `zsh`，稍等一下，就可以看到效果了。我的配置文件使用了 `powerline10k` 这个主题，并且按照我自己的习惯添加了一些别名 `alias` 配置，同时选用了 `powerline10k` 在不需要字体依赖依然能够正常享用的`p10k.zsh`配置。

**如果你知道如何安装并应用字体依赖的话，推荐尝试下面这个主题配置**

这是一个类似于 `agnoster`  的风格配置，不仅显示效果好，针对各种系统都有对应的图标显示。而且主题提供了预加载模式，在进入大型Git仓库的时候也能顺畅。

```bash
#在上面的基础上重新下载配置文件 .p10k.zsh 覆盖即可
wget https://raw.githubusercontent.com/techstay/dotfiles/master/zsh/.p10k.zsh
```

如果你在使用过程中没有遇到无法显示的乱码字符，说明字体 **应用成功**

## 注解与参考

### 参考

> 前人栽树后人乘凉...

[使用antigen轻松打造赏心悦目的shell环境](https://cloud.tencent.com/developer/article/1607239)

[Quick start from official wiki document](https://github.com/zsh-users/antigen/wiki/Quick-start)

### 注解

[^1]: [Powerline 字体主页](https://github.com/powerline/fonts)
[^2]: [nerd-font 字体主页](https://github.com/ryanoasis/nerd-fonts)