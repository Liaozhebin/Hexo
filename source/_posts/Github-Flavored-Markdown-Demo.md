---
title: Github Flavored Markdown Demo 
tags:
  - Demo
  - Github
categories:
  - cate
  - cate2
copyright: true
permalink: false
top: false
date: 2020-03-03 16:35:23
password:
---

**README**
该文件用来测试和展示书写编写博客时需要用到的各种markdown语法。GitHub的markdown语法在标准的markdown语法基础上做了扩充，称之为`GitHub Flavored Markdown`。简称`GFM`，GFM在GitHub上有广泛应用，除了README文件外，issues和wiki均支持markdown语法。
<!---more--->

****
## 目录
* [目录](#%E7%9B%AE%E5%BD%95)
* [文章编辑](#%E6%96%87%E7%AB%A0%E7%BC%96%E8%BE%91)
* [文本](#%E6%96%87%E6%9C%AC)
* [文本块](#%E6%96%87%E6%9C%AC%E5%9D%97)
* [文字高亮](#%E6%96%87%E5%AD%97%E9%AB%98%E4%BA%AE)
* [换行](#%E6%8D%A2%E8%A1%8C)
* [斜体、粗体、删除线](#%E6%96%9C%E4%BD%93%E7%B2%97%E4%BD%93%E5%88%A0%E9%99%A4%E7%BA%BF)
* [图片](#%E5%9B%BE%E7%89%87)
* [链接](#%E9%93%BE%E6%8E%A5)
* [列表](#%E5%88%97%E8%A1%A8)
* [引用](#%E5%BC%95%E7%94%A8)
* [代码高亮](#%E4%BB%A3%E7%A0%81%E9%AB%98%E4%BA%AE)
* [表格](#%E8%A1%A8%E6%A0%BC)
* [diff语法](#diff%E8%AF%AD%E6%B3%95)
* [转义字符：](#%E8%BD%AC%E4%B9%89%E5%AD%97%E7%AC%A6)
* [HTML定义的样式：](#html%E5%AE%9A%E4%B9%89%E7%9A%84%E6%A0%B7%E5%BC%8F)
  * [字体颜色与字体大小](#%E5%AD%97%E4%BD%93%E9%A2%9C%E8%89%B2%E4%B8%8E%E5%AD%97%E4%BD%93%E5%A4%A7%E5%B0%8F)
  * [字体背景颜色](#%E5%AD%97%E4%BD%93%E8%83%8C%E6%99%AF%E9%A2%9C%E8%89%B2)
  * [&lt;video&gt; 标签](#video-%E6%A0%87%E7%AD%BE)
  * [&lt;embed&gt; 标签](#embed-%E6%A0%87%E7%AD%BE)
  * [&lt;iframe&gt; 标签](#iframe-%E6%A0%87%E7%AD%BE)
* [Hexo博客系统扩展的语法：](#hexo%E5%8D%9A%E5%AE%A2%E7%B3%BB%E7%BB%9F%E6%89%A9%E5%B1%95%E7%9A%84%E8%AF%AD%E6%B3%95)
  * [字体居中](#%E5%AD%97%E4%BD%93%E5%B1%85%E4%B8%AD)
  * [Note标签](#note%E6%A0%87%E7%AD%BE)
  * [Tags 选项卡](#tags-%E9%80%89%E9%A1%B9%E5%8D%A1)
  * [按钮Botton](#%E6%8C%89%E9%92%AEbotton)
  * [添加的功能](#%E6%B7%BB%E5%8A%A0%E7%9A%84%E5%8A%9F%E8%83%BD)
    * [折叠文本：](#%E6%8A%98%E5%8F%A0%E6%96%87%E6%9C%AC)
* [标题](#%E6%A0%87%E9%A2%98)
* [参考：](#%E5%8F%82%E8%80%83)


## 文章编辑
### 文章简介生成：

    在文章中使用 `<!--more-->` 手动截断来生成简介。
### 分割线
`***`、`---`、`___`可以显示横线效果

***
---
___


## 文本
### 字段缩进：

使用转义符 `&emsp;&emsp;` 或者 `全角空格` 来进行缩进

**示例：**

```
&emsp;&emsp;这是首行缩进的文本
　　这是全角空格的字符缩进
```
**效果预览：**
&emsp;&emsp;这是首行缩进的文本
　　这是全角空格的字符缩进

### 小文本/大文本：

在文本两端分别加入 `<small>` 和 `</small>`或 `<big>`和`</big>`  即可生成小文本

**示例：**    
`<small>小文本</small>`和 `<big>大文本</big>`

**预览效果**    
<small>小文本</small>和<big>大文本</big>


## 文本块
### 单行文本块

**示例：**    
在一行开头加入1个Tab或者4个空格。

**演示效果：**    

    Hello,大家好，我是果冻虾仁。

### 多行文本块
**语法示例1：**
在连续几行的文本开头加入1个Tab或者4个空格。

**演示效果：**

    欢迎到访
    很高兴见到您
    祝您，早上好，中午好，下午好，晚安

**语法示例2：**
使用一对各三个的反引号：

**演示效果：**

```
欢迎到访
我是zhrbin
这是一个Markdown语法展示
```
该语法也可以实现代码高亮，见[代码高亮](#代码高亮)
## 文字高亮
文字高亮功能能使行内部分文字高亮，使用一对反引号。

**示例：**
```
`linux` `网络编程` `socket` `epoll` 
```
**效果预览：**
`linux` `网络编程` `socket` `epoll`
也适合做一篇文章的tag

## 换行
直接回车不能换行，  
可以在上一行文本后面补两个空格，  
这样下一行的文本就换行了。

或者就是在两行文本直接加一个空行。

也能实现换行效果，不过这个行间距有点大。

## 斜体、粗体、删除线
- 倾斜：在文本两端各加`一个*`号
- 加粗：在文本两端各加`两个*`号
- 删除线：需要在文本两端各加`两个~~`
- 同时倾斜加粗删除线：在文本两端各加`三个*`和`2个~~`号
- 斜体、粗体、删除线可混合使用

|示例|效果|
|----|-----|
|`*斜体1*`|*斜体1*|
|`_斜体2_`| _斜体2_|
|`**粗体1**`|**粗体1**|
|`__粗体2__`|__粗体2__|
|`这是一个 ~~删除线~~`|这是一个 ~~删除线~~|
|`***斜粗体1***`|***斜粗体1***|
|`___斜粗体2___`|___斜粗体2___|
|`***~~斜粗体删除线1~~***`|***~~斜粗体删除线1~~***|
|`~~***斜粗体删除线2***~~`|~~***斜粗体删除线2***~~|



## 图片

基本格式：  `![alt](URL title)`

- `alt`和`title`即对应HTML中的`alt`和`title`属性（都可省略）：
- `alt`表示图片显示失败时的替换文本
- `title`表示鼠标悬停在图片时的显示文本（注意这里要加引号）

URL即图片的url地址，如果引用本仓库中的图片，直接使用**相对路径**就可了，如果引用其他github仓库中的图片要注意格式，即：`绝对路径链接`

| #    | 语法 | 效果 |
| ---- | ---- | ---- |
|   1   | ` ![baidu](http://www.baidu.com/img/bdlogo.gif "百度logo")` | ![baidu](http://www.baidu.com/img/bdlogo.gif "百度logo") |
| 2 | `![][link-name]`                                            |      |

- 注意：   
例2的写法使用了**URL标识符引用**的形式，`[link-name]`作为变量名被引用。
这种方式能达到复用的目的，一般把全文所有的 URL 链接统一放在文章末尾，这样看起来比较干净。
>在文末对`link-name`进行定义：
```
[link-name]:https://img-blog.csdnimg.cn/201908060004034.png
```

## 链接
超链接形式和图片类似，删掉前面的 `!` 即可
### 链接本地的URL

|语法|效果|
|----|-----|
|`[我的简介](/example/profile.md)`|[我的简介](/example/profile.md)|
|`[example](./example)`|[example](./example)|

### 锚点
其实呢，每一个标题都是一个锚点，和HTML的锚点（`#`）类似，比如我们 

|语法|效果|
|---|---|
|`[回到顶部](#readme)`|[回到顶部](#目录)|

不过要注意，标题中的英文字母都被转化为**小写字母**了。
> 以前GitHub对中文支持的不好，所以中文标题不能正确识别为锚点，但是现在已经没问题啦！

## 列表
### 无序列表
**示例：**
```
* 昵称：果冻虾仁
- 别名：隔壁老王
* 英文名：Jelly
```
**效果预览：**
* 昵称：果冻虾仁
- 别名：隔壁老王
* 英文名：Jelly

### 多级无序列表
**示例：**
```
* 用星号`*`标记列表
    * 脚本语言
        * Python
```
**效果预览：**
* 用星号`*`标记列表
    * 脚本语言
        * Python

### 一级有序列表
**示例：**
就是在数字后面加一个点，再加一个空格。不过看起来起来可能不够明显。 
```
面向对象的三个基本特征：

1. 封装
2. 继承
3. 多态
```

**效果预览：**
面向对象的三个基本特征：

1. 封装
2. 继承
3. 多态


### 多级有序列表
和无序列表一样，有序列表也有多级结构。
**示例：**
```
1. 这是一级的有序列表，数字1还是1
   1. 这是二级的有序列表，阿拉伯数字在显示的时候变成了罗马数字
      1. 这是三级的有序列表，数字在显示的时候变成了英文字母
```

**效果预览：**

1. 这是一级的有序列表，数字1还是1
   1. 这是二级的有序列表，阿拉伯数字在显示的时候变成了罗马数字
      1. 这是三级的有序列表，数字在显示的时候变成了英文字母
	

### Checkbox 复选框列表
**示例：**
```
- [x] 需求分析
- [x] 系统设计
- [x] 详细设计
- [ ] 编码
- [ ] 测试
- [ ] 交付
- [x] 这是选中的状态
- [ ] 这是未选中状态，注意中间空格不能丢

```
**效果预览：**

- [x] 需求分析
- [x] 系统设计
- [x] 详细设计
- [ ] 编码
- [ ] 测试
- [ ] 交付
- [x] 这是选中的状态
- [ ] 这是未选中状态，注意中间空格不能丢


您可以使用这个功能来标注某个项目各项任务的完成情况。
> Tip:
>
> > 在GitHub的**issue**中使用该语法是可以实时点击复选框来勾选或解除勾选的，而无需修改issue原文。

## 引用
语法：用 ` > ` 号标记，有多级结构
**示例：**
```
> 数据结构
>> 树
>>> 二叉树
>>>> 平衡二叉树
>>>>> 满二叉树
```
**效果预览：**
> 数据结构
> > 树
> > > 二叉树
> > > > 平衡二叉树
> > > >
> > > > > 满二叉树

## 代码高亮
**示例：**
在三个反引号后面加上编程语言的名字，另起一行开始写代码，最后一行再加上三个反引号。

**效果预览：**

```Java
public static void main(String[]args){} //Java
```
```c
int main(int argc, char *argv[]) //C
```
```Bash
echo "hello GitHub" #Bash
```
```javascript
document.getElementById("myH1").innerHTML="Welcome to my Homepage"; //javascipt
```

## 表格
### 标准语法
**示例：**
```
| 表头1  | 表头2|
| ---------- | -----------|
| 表格单元   | 表格单元   |
| 表格单元   | 表格单元   |
```
**效果预览：**

| 表头1  | 表头2|
| ---------- | -----------|
| 表格单元   | 表格单元   |
| 表格单元   | 表格单元   |

### 非标准语法
**示例：**
```
表头1  | 表头2
--------- | --------
表格单元  | 表格单元 
表格单元  | 表格单元 
```
**效果预览：**
表头1  | 表头2
--------- | --------
表格单元  | 表格单元 
表格单元  | 表格单元 


### 对齐
表格可以指定对齐方式，其中第二行表示对齐方式

- 默认为左对齐，只写 `-`
- 居中为 `:-:`
- 右对齐为 `-:`

**示例：**
```
| 左对齐 | 居中  | 右对齐 |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |
```
**效果预览：**
| 左对齐 | 居中  | 右对齐 |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |

### 混合其他语法
表格单元中的内容可以和其他大多数GFM语法配合使用，如：  
**使用普通文本的删除线，斜体，嵌入图片等效果**

| 名字 | 描述 |
| ------------- | ----------- |
| Help      | ~~Display the~~ help window.|
| Close     | _Closes_ a window     |



## diff语法

版本控制的系统中都少不了diff的功能，即展示一个文件内容的增加与删除。
GFM中可以显示的展示diff效果。使用绿色表示新增，红色表示删除。
### 语法
其语法与代码高亮类似，只是在三个反引号后面写diff，
并且其内容中，可以用 `+ ` 开头表示新增，`- ` 开头表示删除。
另外还有有 `!` 和 `#` 的语法。

#### 效果预览：

```diff
+ 人闲桂花落，
- 夜静春山空。
! 月出惊山鸟，
# 时鸣春涧中。
```
## 转义字符：

**示例：**
```
\#
\*
\!
\+
\-
```
**效果预览：**
\#
\*
\!
\+
\-

## HTML定义的样式：
### 字体颜色与字体大小

- Hexo只支持黑色字体，可以使用Html语言调整颜色，使用 `<font color="ff0000">` 和`</font>` 包裹需要变色的字体，ff0000可以替换为其他颜色代码。
- 字号同样使用Html语言调整，使用 `<font size=12>` 和 `</font>` 包裹需要改变大小的字体，font size=后是调整的字号。
- 字体同样使用Html语言调整，使用 `<font face="华文彩云">` 和 `</font>` 包裹需要改变的字体，font face=后是调整的字体名称。
- 颜色字号字体三者可以叠加使用

**示例：**
```
<font color="ff0000">这是红色字</font>
<font size=2>这是2号字</font>
<font face="华文彩云">这是华文彩云字</font>
<font face="华文彩云" size=2 color="ff0000">这是2号红色华文彩云字</font>
```
**预览效果：**
> <font color="ff0000">这是红色字</font>
> <font size=2>这是2号字</font>
> <font face="华文彩云">这是华文彩云字</font>
> <font face="华文彩云" size=2 color="ff0000">这是2号红色华文彩云字</font>

### 字体背景颜色

文字背景色使用HTML表格来设置，在`bgcolor`后设置文字背景色，使用颜色英文名
**示例：**

```xml
<table><tr><td bgcolor=lightblue>背景色yellow</td></tr></table>
```
**效果预览：**

<table><tr><td bgcolor=lightblue>亮蓝色背景色</td></tr></table>
## 视频的插入：

音乐和视频建议上传到B站或Youtube等平台，通过HTML标记语言嵌入，直接复制网页提供的分享链接即可，使用`width`设置宽度，`height`设置高度。

### `<video>` 标签
使用`source src`设置视频路径

**示例：**

```xml
<video width="480" height="320" controls>
<source src="movie.mp4">
</video>
```

**预览： ~~（并没有视频）~~**

<video width="480" height="320" controls>
<source src="https://static.cdn.soulapp.cn/video/m_video.mp4">
</video>

### `<embed>` 标签

**示例：**

```xml
<embed src='https://player.youku.com/player.php/sid/XMzUzNjg1OTQzNg==/v.swf' allowFullScreen='true' quality='high' width='480' height='400' align='middle' allowScriptAccess='always' type='application/x-shockwave-flash'></embed>
```

**预览：（随便放的）**
<embed src='https://player.youku.com/player.php/sid/XMzUzNjg1OTQzNg==/v.swf' allowFullScreen='true' quality='high' width='480' height='400' align='middle' allowScriptAccess='always' type='application/x-shockwave-flash'></embed>
### `<iframe>` 标签
**示例：**

```xml
<iframe height=400 width=600 src="//player.bilibili.com/player.html?aid=11171478&cid=23141162&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
```

**预览：**

<iframe height=400 width=600 src="//player.bilibili.com/player.html?aid=11171478&cid=23141162&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
## 表情
Github的Markdown语法支持添加emoji表情，输入不同的符号码（两个冒号包围的字符）可以显示出不同的表情。
比如`:Blush；`，可以显示:blush:。

具体每一个表情的符号码，可以查询GitHub的官方网页[http://www.emoji-cheat-sheet.com](http://www.emoji-cheat-sheet.com)。



## Hexo博客系统扩展的语法：
### 字体居中
字体居中使用Html语言包裹，有三种格式
**示例：**

```xml
{% centerquote %}这是居中字体{% endcenterquote %}
 <blockquote class="blockquote-center">这是居中字体</blockquote>
{% cq %}这是居中字体{% endcq %}
```
**效果预览：**
{% centerquote %}这是居中字体{% endcenterquote %}

 <blockquote class="blockquote-center">这是居中字体</blockquote>
{% cq %}这是居中字体{% endcq %}

### Note标签
需要在 `Next` 主题配置中搜索 `Note tag` 开启，共有5种`style`，预览可以在[这里](https://github.com/iissnan/hexo-theme-next/pull/1697)查看，`icon`用于设置是否显示图标。

**示例：**

使用 `<div>` 包裹需要显示的内容，`class` 后面显示 `note` 的风格，加上 `no-icon` 可以隐藏图标

```xml
<div class="note default"><p>default</p></div>
<div class="note primary"><p>primary</p></div>
<div class="note success"><p>success</p></div>
<div class="note info"><p>info</p></div>
<div class="note warning"><p>warning</p></div>
<div class="note danger"><p>danger</p></div>
<div class="note default no-icon"><p>danger no-icon</p></div>
```

**效果预览：**
<div class="note default"><p>default</p></div>
<div class="note primary"><p>primary</p></div>
<div class="note success"><p>success</p></div>
<div class="note info"><p>info</p></div>
<div class="note warning"><p>warning</p></div>
<div class="note danger"><p>danger</p></div>
<div class="note default no-icon"><p>danger no-icon</p></div>
### Tags 选项卡

需要在 `Next` 主题中将 `enable` 设置为 `true` 开启

#### 样式一

**示例：**

```xml
{% tabs First unique name %}
<!-- tab -->
**This is Tab 1.**
<!-- endtab -->
<!-- tab -->
**This is Tab 2.**
<!-- endtab -->
<!-- tab -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}
```



**效果预览：**
{% tabs First unique name %}
<!-- tab -->
**This is Tab 1.**
<!-- endtab -->
<!-- tab -->
**This is Tab 2.**
<!-- endtab -->
<!-- tab -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}



#### 样式二

**示例：**
第一行的数字3表示默认显示的Tabs,设置为-1时表示不显示默认Tabs

```xml
{% tabs Second unique name, 3 %}
<!-- tab -->
**This is Tab 1.**
<!-- endtab -->
<!-- tab -->
**This is Tab 2.**
<!-- endtab -->
<!-- tab -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}
```



**效果预览：**
{% tabs Second unique name, 3 %}
<!-- tab -->
**This is Tab 1.**
<!-- endtab -->
<!-- tab -->
**This is Tab 2.**
<!-- endtab -->
<!-- tab -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}



#### 样式三

**示例：**
选项的名称和图标可以自定义，在`<!-- tab 自定义名称@自定义图标 -->`中调整

```xml
{% tabs Third unique name %}
<!-- tab Solution 1@text-width -->
**This is Tab 1.**
<!-- endtab -->
<!-- tab Solution 2@amazon -->
**This is Tab 2.**
<!-- endtab -->
<!-- tab Solution 3@bold -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}
```

**效果预览：**
{% tabs Third unique name %}
<!-- tab Solution 1@text-width -->
**This is Tab 1.**
<!-- endtab -->
<!-- tab Solution 2@amazon -->
**This is Tab 2.**
<!-- endtab -->
<!-- tab Solution 3@bold -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}



### 按钮Botton

**示例：**
使用`button`或者`btn`，在两者后面加入要跳转的链接，不加链接的话默认跳转到当前页面

```xml
//只显示文字，Text是文字内容
{% button https://siriusq.top/, 主页 %}

//多个按钮并列
{% btn https://siriusq.top/, 主页 %} {% btn #, Text & Title,, Title %}

//只显示图标
<p>{% btn https://siriusq.top/,, home fa-5x %}
{% btn #,, home fa-4x %}
{% btn #,, home fa-3x %}{% btn #,, home fa-2x %}{% btn #,, home fa-lg %}{% btn #,, home %}</p>

//显示文字和图标
<p>{% btn #, Text & Icon (buggy), home %}
{% btn #, Text & Icon (fixed width), home fa-fw %}</p>
```

**效果预览：**
//只显示文字，Text是文字内容
{% button https://siriusq.top/, 主页 %}

//多个按钮并列
{% btn https://siriusq.top/, 主页 %} {% btn #, Text & Title,, Title %}

//只显示图标
<p>{% btn https://siriusq.top/,, home fa-5x %}
{% btn #,, home fa-4x %}
{% btn #,, home fa-3x %}{% btn #,, home fa-2x %}{% btn #,, home fa-lg %}{% btn #,, home %}</p>

//显示文字和图标
<p>{% btn #, Text & Icon (buggy), home %}
{% btn #, Text & Icon (fixed width), home fa-fw %}</p>


### 添加的功能
#### 折叠文本：
**示例：**
```bash
{% fold 点击显/隐内容 %}
something you want to fold, include code block.
{% endfold %}
```

**效果预览：**
{% fold 点击显/隐内容 %}
something you want to fold, include code block.
{% endfold %}

## 标题
在文字前加#和空格，支持六级标题和大小标题，一定不要漏了 空格，空格漏掉的话会和普通字符一样显示

## 一级标题  
## 二级标题  
### 三级标题  
#### 四级标题  
##### 五级标题  
###### 六级标题  

## 参考：

- 果冻虾仁 Jelly.K.Wang@qq.com
- [Markdown写作语法](https://siriusq.top/Markdown%E5%86%99%E4%BD%9C%E8%AF%AD%E6%B3%95.html)

--------------------------------
[csdn]:http://blog.csdn.net/guodongxiaren "我的博客"
[zhihu]:https://www.zhihu.com/people/jellywong "我的知乎，欢迎关注"
[weibo]:http://weibo.com/linpiaochen
[baidu-logo]:http://www.baidu.com/img/bdlogo.gif "百度logo"
[weibo-logo]:/img/weibo.png "点击图片进入我的微博"
[csdn-logo]:/img/csdn.png "我的CSDN博客"
[code-past]:https://img-blog.csdnimg.cn/201908060004034.png

