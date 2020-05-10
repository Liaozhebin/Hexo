---
title: Zsh，一款现代化的 Linux Shell 终端
date: 2020-04-26 
updated: 2020-05-03 
urlname: Zsh_and_oh-my-zsh
tags:
  - Shell
  - Linux
  - Zsh
  - oh-my-zsh
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

**README**
本文介绍了 `Zsh`是什么，与传统的bash有什么不同，如何安装并使用，`Shell`的概念，以及zsh的配置集`oh-my-zsh`的主题与插件的使用。
`zsh` 是一款 **成熟稳定，现代化**的 shell，兼容于传统的 bash  sh 的同时，比它们拥有更强大的功能。以至于苹果系统已将 zsh 取代 bash 作为系统默认的 `shell` 了[^1].
`oh-my-zsh`集成了 zsh 的 配置文件、主题 Themes、插件 Options，使任何人可以轻松的配置出一个 **beautiful & friendly** 的 zsh，来提高生产效率。包括更智能的色彩高亮，历史目录快速跳转，kill 进程名按 tab 键 自动转 PID 等自动补齐功能。
<!---more--->

------


> **序言：**
>广受本视频启蒙，特放此处，可以看作为本文的导览版视频，本文是根据此视频的基础上进行了增强。
> 感谢 `up` 主优先制作了这期视频。
>
> <iframe src="//player.bilibili.com/player.html?aid=78082601&bvid=BV1pJ411B7HY&cid=133593554&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true" height="400px"> </iframe>



## ZSH 是什么

在这之前，你可能需要明白 `shell` 的概念

> `shell` 是机器外面套一层命令行的壳，用于人际交互，`Linux` 下的 `Bash` 和 `sh` 都属于 `shell` 的一种

`zsh` 也是一种 `shell`，兼容于传统的 `bash`  `sh` 的同时，还比它们拥有更强大的功能。

以至于苹果系统 `macOS Catalina` 开始 ，已将 `zsh` 取代 `bash` 作为系统默认的 `shell` 了[^1]，这证明了 `zsh` 是一款 **成熟稳定，现代化 **的 `shell` .

### zsh 兼容性：
<details>
<summary> 💌 点击展开查看 </summary>  

#### 兼容原理：

> zsh 内建了一个仿真模式 emulation mode ，可以对 bash ksh csh 进行仿真，该模式下可以使用与 Bash 相同的语法和命令集，从而达到几乎完全的兼容 输入 `emulate  [ bash | csh | ksh ]` 进入他们的仿真模式。

#### 兼容性的注意事项：

- **echo  命令**

	>  `echo` 是 `Bulit-in` 内置命令，zsh 下要被转义 `2` 次，内建 `bulit-in`一次，输出到终端一次，所以要 用 `-E`  显式指明不转义，以减少一次转义。[^2]

</details>


## oh-my-zsh 是什么

### 博主描述

正如 `bash` 有 `.bashrc` 配置文件，`zsh` 也有他的配置文件 `.zshrc`，而 `oh-my-zsh` 就是由开源社区维护并驱动的一款 `zsh` 配置文件的框架集。

它集成扩展了广大 `zsh` 使用者的一些常用 `配置文件` `主题 Themes` `插件 Options`，使任何人可以轻松的配置出一个 `beautiful & friendly` 的 `zsh`，来提高生产效率。 

包括更智能的色彩高亮，历史目录快速跳转，`kill` 进程名 `tab键` 自动转 `PID`，错误命令 `lls` 修正猜测 `ls` ，更强大的 `tab` 自动补齐功能等。

### 有趣的官方介绍

> Oh My Zsh is an open source, community-driven framework for managing your [zsh](https://www.zsh.org/) configuration.
>
> Sounds boring. Let's try again.
>
> **Oh My Zsh will not make you a 10x developer...but you may feel like one.**
>
> Once installed, your terminal shell will become the talk of the town *or your money back!* With each keystroke in your command prompt, you'll take advantage of the hundreds of powerful plugins and beautiful themes. Strangers will come up to you in cafés and ask you, *"that is amazing! are you some sort of genius?"*
>
> Finally, you'll begin to get the sort of attention that you have always felt you deserved. ...or maybe you'll use the time that you're saving to start flossing more often. 😬



## 安装与使用

### zsh安装

**版本最好 >5 越新越好**

- Debian：`apt-get install zsh fzf && zsh --version && chsh -s $(which zsh)`
- Centos：`yum instasll zsh && zsh --version && chsh -s $(which zsh)`

### oh-my-zsh 安装

`curl` 和 `wget` 二选一

- **via curl** : 

```bash
  sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

- **via wget** ： 

```bash
  sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```



#### 我翻译和优化的 `.zshrc` 文件

虽然配置文件架构很简单，但是我还是翻译了配置文件中的常用选项释义，希望能帮助到 **英文不好** 的你修改出一个适合自己的配置文件。

[文件地址](https://raw.githubusercontent.com/Liaozhebin/files/master/.zshrc)

我的配置文件选用了 `bira` 主题 ，选用的插件有 
```
git fzf history history-substring-search zsh-interactive-cd vi-mode extract pip docker docker-compose alias-finder
```

因为使用了更优秀的 `z.lua` 路径插件，为避免冲突，所以没有选用 `z` 插件，有需要的可以自己添加噢。

##### 下载使用我最新的 .zshrc 配置：

   ```bash
  cd ~ && curl -LO https://raw.githubusercontent.com/Liaozhebin/files/master/.zshrc  && source .zshrc 
   ```



#### 使用内置主题

开始全部看了一下，记录了比较美观整洁的有：`simple` `suvash` `wedisagree`  `ys`  `robbyrussell` [agnoster](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes#agnoster)  [bira  ](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes#bira)，其中 `robbyrussell`是 `oh-my-zsh` 的默认主题，最后选定了以下 `2` 款使用

1. [bira  ](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes#bira) : 2行显示，路径 和 Git 项目状态颜色渲染

2. [agnoster](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes#agnoster)  ： 单行显示，路径文字背景渲染

其中也可以 更改主题名为 `random`，这样每次使用 zsh 终端会随机应用一个**内置**主题，这样可以很方便的体验每一个主题的，并对喜爱的进行收藏。

> 使用外置主题不能使用 `random` 随机参数，此参数只针对内置主题进行随机应用
>
> > [摘自官方wiki](https://github.com/ohmyzsh/ohmyzsh/wiki/Customization#overriding-and-adding-themes)：Note: Using a random theme with `$ZSH_THEME="random"` will not look into your custom themes directory. Only built-in themes will be used. (Until PR [#3743](https://github.com/ohmyzsh/ohmyzsh/pull/3743) is merged, which makes `random` include custom themes.)



#### 安装外部主题

##### 首先解决依赖


1. 保证版本号 zsh >5 ，同时部分主题插件有详细的要求，比如版本 >5.3，详情见其 Documents

2. **非必须** 想要顺利安装使用外部主题，还需要安装字体依赖包 [Powerline fonts](https://github.com/powerline/fonts)

<details><summary>因博主安装字体后不知如何应用字体，所以折叠安装过程</summary> 

- debian、ubuntu：`apt-get install fonts-powerline`

- fedora：`dnf install powerline-fonts`

- other systems：
  ```bash 
    git clone https://github.com/powerline/fonts.git --depth=1
    cd fonts && ./install.sh
    cd .. && rm -rf fonts
  ```
</details>



##### 选用外部主题

外部主题太多了，浏览了前 40%+ 的主题预览图，筛选了以下这些比较讨眼缘的主题：

1.   [zsh2000  ](https://github.com/maverick9000/zsh2000)[类agnoster] 

2. [Daivasmara](https://github.com/ohmyzsh/ohmyzsh/wiki/External-themes) 

3. [Philthy](https://github.com/ohmyzsh/ohmyzsh/wiki/External-themes#philthy-theme) 

4. [Random Emoji Theme](https://github.com/ohmyzsh/ohmyzsh/wiki/External-themes#random-emoji-theme) 

5. [Bullet train](https://github.com/ohmyzsh/ohmyzsh/wiki/External-themes#bullet-train)[2.4k] 

6. [powerlevel10k](https://github.com/ohmyzsh/ohmyzsh/wiki/External-themes#powerlevel10k)[5K] 

7. [Node theme](https://github.com/ohmyzsh/ohmyzsh/wiki/External-themes#node-theme) 

8. [Spaceship ZSH](https://github.com/ohmyzsh/ohmyzsh/wiki/External-themes#spaceship-zsh)[11k]

最后经过粗略的二次对比，最后选择了 [powerlevel10k](https://github.com/ohmyzsh/ohmyzsh/wiki/External-themes#powerlevel10k) 这款拥有 5K+ 收藏量的主题，其实这款主题还有同门一个大兄弟 [powerlevel9k](https://github.com/Powerlevel9k/powerlevel9k)，拥有 12.6K+ Star，因为种种原因[^3]而剥离出了 [powerlevel10k](https://github.com/ohmyzsh/ohmyzsh/wiki/External-themes#powerlevel10k) 这个分支项目，同时兼容于 [powerlevel9k](https://github.com/Powerlevel9k/powerlevel9k) 的配置。

#### 使用 [powerlevel10k](https://github.com/ohmyzsh/ohmyzsh/wiki/External-themes#powerlevel10k) 外部主题：

##### 环境要求：

- 要求 `zsh` 版本 > `5.1`  

-  推荐安装 [Powerline fonts](https://github.com/powerline/fonts) 字体

##### 使用感受：

能显示命令执行花费时间，这点很棒。但是需要完成 [下图的初始化向导](https://raw.githubusercontent.com/romkatv/powerlevel10k-media/master/configuration-wizard.gif) 才能体现出这个主题的优势，所以个人觉得只适合在长期使用的主机上使用，~~不适合在短期使用的云服务器上~~。

> 想在短期的服务器上使用，只需上传主题配置文件 `.p10k.zsh` 到 `~` 根目录即可。或者查看我的另一篇文章 **antigen，zsh的包管理器**。

#####  安装过程：

1. 安装：
```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k`
```
2. vim修改 `.zshrc` 的主题参数为 `powerlevel10k/powerlevel10k` 
```bash
vim ~/.zshrc
source ~/.zshrc
```
3. 输入 `p10k configure` 进入主题配置向导，配置好后的配置文件保存在 `~/.p10k.zsh` 中，如果这个文件不存在，正常情况下会启用初始化配置向导。（如下图）![配置向导演示](https://raw.githubusercontent.com/romkatv/powerlevel10k-media/master/configuration-wizard.gif)

4. enjoy it to the max

#### 使用插件

##### 内置插件

[oh-my-zsh 内置插件列表](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins)

###### 自己选用的插件如下

- `git fzf history-substring-search zsh-interactive-cd vi-mode extract pip docker docker-compose alias-finder`
  
1. `history`  别名插件 [Readme](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/history)

   > | Alias | Command             |
   > | ----- | ------------------- |
   > | `h`   | `history`           |
   > | `hs`  | `history | grep`    |
   > | `hsi` | `history | grep -i` |

2. `zsh-history-substring-search` 

   > 输入历史记录命令中的任何部分，然后按选定的键（`UP` 和 `DOWN` 箭头）来循环进行匹配。[Readme](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/history-substring-search)

3. `extract`  [Readme](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/extract)
  
   > 插件定义了一个名为的 `extract` 的函数，可以使用统一的 `extract` 命令解压多种类型的压缩文件，这样，您就不必知道要使用哪个特定命令来提取压缩文件。
  
4. `git` 别名插件 [Readme](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/git)
  
5. `zsh-interactive-cd` [Readme](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/zsh-interactive-cd)
  
   > 此插件是 `fzf` 与 `cd` 结合的交互式路径模糊过滤插件，类似于 `z -I .` 的效果    >
   > **使用** ： 输入 `cd` 后按 `control + o` 激活




###### 其他值得一试的内置插件

1. `z` 是路径快速跳转插件，类似于 z.lua z.sh autojump
2. `timer` 是显示命令执行时间的插件。
3. `adb` 是 adb 的命令补全插件。
4. `cp` 是rsync的简化插件。
5. `tmux` 是 tmux 的 alias 别名插件。
6. `web-search plugin`：适合桌面用户，方便的打开输入关键词打开对应搜索引擎，类似于 Listary 的网页搜索。
7. `command-not-found` [Readme](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/command-not-found)
  
     > 这是一个当你运行 `一个未知 or 错误命令` 时，插件会自动提示你可能需要安装相关名字的软件包

##### 外部扩展插件

[Awesome-zsh-plugins  外部扩展插件列表 ](https://github.com/unixorn/awesome-zsh-plugins)

外部插件可能需要 **手动下载安装**（而非主题直接下载到目录的方式），如 `z.lua`  `zsh-autosuggestion`

似乎不错的外置插件：

- ` mysql-colorize` mysql 命令着色插件似乎不错。

##### 安装 `zsh-autosuggestion` 插件

这是一个类似 `fish` 命令提示的外置插件，它会根据您的历史命令记录建议您键入的命令。

> 演示效果：
> <a href="https://asciinema.org/a/37390" target="_blank"><img src="https://asciinema.org/a/37390.png" width="400" text-align="center" /></a>

###### 安装步骤 

[Install Readme](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md)

1. Clone this repository into `$ZSH_CUSTOM/plugins` (by default `~/.oh-my-zsh/custom/plugins`)

   ```
   git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
   ```

2. Add the plugin to the list of plugins for Oh My Zsh to load (inside `~/.zshrc`):

   ```
   plugins=(zsh-autosuggestions)
   ```

3. Start a new terminal session.

#### 总结：


外部主题或者插件文件添加到 `./oh-my-zsh` 下的 `plugins` 或 `themes` 文件夹中，回到 `~/.zshrc` 修改对应的主题插件名字后， `source` 引用即可（插件一般需要新建对应插件名的目录后放置文件） 



### z.lua 的安装

#### z.lua 介绍

`z.lua` 是一个快速路径切换工具（类似 z.sh / autojump / fasd），兼容 Windows 和所有 Posix Shell 以及 Fish Shell 的同时包含了众多改进，它会跟踪你在 `shell` 下访问过的路径，经过一段简短的学习之后，`z.lua` 会帮你跳转到所有匹配正则关键字的路径里 `Frecent` 值最高的那条路径去，比如：`z foo bar`  可以匹配到  `/foo/bar`  

[Z.lua zh-cn Readme 中文说明](https://github.com/skywind3000/z.lua/blob/master/README.cn.md)

#### 正式安装

1. 安装 lua ： 
    ```
    apt install -y fzf lua5.3 && mv /usr/bin/lua5.3 /usr/bin/lua
    ```
2. 同步我最新的 .zshrc 配置：
   ```
   cd ~ && curl -LO https://raw.githubusercontent.com/Liaozhebin/files/master/.zshrc  && source .zshrc
   ```
3. 下载 z.lua：
   ```
   cd ~ && curl -LO https://raw.githubusercontent.com/skywind3000/z.lua/master/z.lua && chmod 777 ./z.lua && mv ./z.lua $ZSH_CUSTOM/ && echo 'eval "$(lua      $ZSH_CUSTOM/z.lua --init zsh once enhanced)"' >> ~/.zshrc && echo  source ~/.zshrc
   ```
4. 添加 z.lua 的 alias
   ```
echo ' alias zz="z -i"    # 使用交互式选择模式  \n alias zf="z -I"      # 使用 fzf 对多个结果进行选择  \n alias zft="z -I -t"   # 按时间权重排序 \n alias zb="z -b -i"      # 快速回到父目录  \n alias zbf="z -b -f"     # 使用 fzf 进行父目录筛选 \n ' >> ~/.zshrc && echo  source  ~/.zshrc
   ```

#### **`lua` not found error:**

if notice lua not found ，please install lua & add alias to .zshrc or rename lua bin file，such as ：

 如果提示找不到 lua 安装后添加对应版本 alias 或 重命名 lua，例如：

>  `alias lua='lua5.3'` or  `mv /usr/bin/lua5.3 /usr/bin/lua`











## 注解与参考
### 参考
> 前人栽树后人乘凉...

[知乎专栏：你明白 shell、bash 和 zsh 等词的真正含义吗？](https://zhuanlan.zhihu.com/p/34197680)

[字体依赖包 Powerline fonts](https://github.com/powerline/fonts)

[Oh My ZSH!还在被命令行折腾的死去火来吗？这款软件用过的都说好！](https://www.bilibili.com/video/BV1pJ411B7HY?from=search&seid=2756247263367460073)

### 注解
[^1]:[取代 bash，macOS Catalina 使用 zsh 作为默认 Shell](https://www.oschina.net/news/107223/macos-catalina-zsh-bash-shell-replacement)
[^2]:[Zsh和Bash究竟有何不同](https://blog.csdn.net/lixinze779/article/details/81012318)
[^3]:[Powerlevel9k和Powerlevel10k之间是什么关系？](https://github.com/romkatv/powerlevel10k#what-is-the-relationship-between-powerlevel9k-and-powerlevel10k)


