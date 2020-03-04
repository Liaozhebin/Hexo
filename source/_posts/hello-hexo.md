---
title: hello hexo
date: 2020-03-01 18:04:46
tags:
  - Hello
  - Demo
categories:
  - cate
  -	democate
copyright: true
permalink: false
top: false
password:
---



**==这里是目录，可以快速跳转==**

[TOC]
<!-- toc -->
<!-- more -->
## 临时链接


## 自助工具放前头

1. [查询宽带网络运营商](https://www.ipip.net/ip.html)
2. [查询国外网站可访问情况](https://ip.skk.moe/)；[备用站点](http://ip111.cn)



## 节点说明

### ✔导入节点说明(添加节点说明)：

> 因V2Ray设置较复杂，以后如无特殊情况，统一从采用`从剪切板导入`的方式给大家批量添加节点

#####　从剪切板导入的使用指南：

​	复制一大长串你看不懂的 “有序字符”，然后点击从剪切板导入即可一次性添加所有节点信息

> 大长串你看不懂的“有序字符”，长下面这个样子，仅仅是举例，这个不是有效节点。
>
> `vmess://ew0KICAidiI6ICIyIiwNCigInBzIjogIjAx56aBW+eUtUErXVvnp7tTXVvogZTXea0m+adieeftiIsDQogICJhZGQiOiAiZ2lhZ2lzLjIwMjB5ZWFyLmNmIiNCiAgInBvcnQiOiAiNDQzIiwNCiAgImlkIjogII2YTMwMDZjLWJkMWMtOllNS03GU4LWJjZGJmZjdmOGVhNiIsDQogICJhaWQiOiAiNisDQogICJuZXQiOiAid3MiLA0KCAidHlwZSI6ICJub25lIiwNCiAgImhvc3QiiAiZ2lhZ2lzLjIwMjB5ZWFyLmNmiwNCiAgInBhdGgiOiAiL2JpbmdPMC92bWVzcyIsDQgICJ0bHMiOiAidGxzIg0KfQ==`



### 节点信息：

##### 等级划分：

##### 						S > A+ > A > A- > B+ > B > B- > C+ > C

​		注意：不绝对，只是引导作用，一般情况下都可以按等级标识来使用，连接效果不好时换节点类型试试

##### 运营商标识：

​				[电]=电信；[移]=移动；[联]=联通

##### 节点名称标识含义：

- **==禁：高级节点，严禁滥用；严禁走代理下载大文件(3GB)；禁止看2K(不含)以上视频==（特别是移动S级节点)**
- **转**：表示`中转服务器`，使用国内借道中转<电信or联通>的方式给移动加速   example：`04转02`  表示   `使用中转方式使用02节点`
- **数字**：服务器编号标识，数字一样代表服务器一样



- ~~**可**：可以自由使用。
**特**[^3]：使用了特别的网络协议，可使网络质量提升一个等级(example：[B-] 变为 [A-])，**值得一试（特别是==移动用户==）**（部分地区运营商无效，电信联通在网络不好的时候也可以试试）~~  



---------------



## ✔客户端使用说明 ==请详细阅图==

### 安卓客户端

安卓客户端分成2张图进行说明，分别为`主界面`和`设置界面`

> 1. 导入节点
> 2. 修改设置(见设置界面)
> 3. 测试`全部配置真连接`，根据结果选择合适的节点
> 4. enjoy it ...

【主界面图】：

> ![安卓主界面.png](https://i.loli.net/2020/02/03/ZV7suntNBI4OeFr.png)

【设置界面】：

> ![安卓设置页.png](https://i.loli.net/2020/02/02/CVq67BwTGcXtymf.png)





### PC客户端

##### PC杀毒安全软件问题：

条件允许的话，还请大家尽量不要使用`360软件`，推荐一些更好的`免费安全软件`：

> 1. [知乎话题---你认为哪款 Windows 杀毒软件最好？](https://www.zhihu.com/question/21085687?sort=created)
>
> 2. [Avast](https://www.avast.com/zh-cn/index)：[**强推**]来自捷克的一款优秀杀毒软件
>
> 3. [Windows Defender](https://www.microsoft.com/en-us/windows/comprehensive-security)：Windows10系统内置杀毒软件，也是非常优秀的，意味着Win10可以不用装杀毒软件也可以很好的保证安全。
>
> 4. [火绒安全](https://www.huorong.cn/person5.html)：国产
>
> > [知乎话题---360 杀毒的真实水平怎么样？](https://www.zhihu.com/question/64616904)
> >
> > [知乎话题---到底要不要下载360安全卫士？](https://www.zhihu.com/question/328342935/answer/708544558)

#### PC客户端说明正文

PC客户端使用`右下角托盘`和`主界面`图进行说明：

> 1. 解压压缩包
> 2. 打开文件夹里的`v2rayN.exe`
> 3. 看`右下角托盘图`进行设置，选择`节点`并选择`PAC代理`模式
> 4. 其他更多操作参考主界面图 `服务器速度测试`&&`服务器延迟测试`
> 5. enjoy it ...

【主界面图】：

> ![PC-主界面解释.png](https://i.loli.net/2020/02/03/GDrT3aVQYxnqN2F.png)

【右下角托盘图】：

> ![PC-托盘解释.png](https://i.loli.net/2020/02/02/XoshcCP5iOAnrRt.png)



### Q&A PC客户端存在的问题

个人测试发现，PC客户端似乎存在一定的不稳定性：

- 频繁切换节点会导致上一个节点再也无法连接上，需要关闭客户端重新打开，甚至重启电脑



## （爱看不看）对移动网络的小吐槽

一直知道移动的出国环境不太好，每次升级节点都因此搞到头疼（想着如何改善一下）

移动不好用，用的人还挺多，搞不懂（似乎也没便宜多少，也就宽带便宜甚至免费）

这次使用了最高等级的`CN2-GIA线路`[^1]和特别的`UDP协议`[^2]，不知道改善如何，` 01节点 ` 使用下来，感觉还不错的话，后期可以考虑增加一个01节点类型的服务器，同时，吐槽移动的出国流量是真滴贵，01节点流量达0.25元/GB，请移动的且用且珍惜。

反观联通和电信：就这次的节点服务器，都是可以用的很舒服的了。

`2020年2月2日 Up to date`



**不过移动会这样还是有他自己的现实原因的：**

> 便宜(一分钱一分货) + 用户**巨**多（中国第一用户保有量，最低海底光缆拥有者，出国海底光缆承载量有限，人均少）
>
> 随便引用一篇知乎的片段：[原文：中国大陆目前国际网络的建设状况](https://zhuanlan.zhihu.com/p/64467370)
>
> ![吐槽.png](https://i.loli.net/2020/02/02/VeTWI5rhB1tYqMo.png)



#### 把吐槽浓缩成一句话

**==总的来说，就是想跟所处移动环境的你们，有条件的话，尽量还是选择联通或者电信网络吧....==**


```bash
cd hexo
ls -lh
git clone https://github.com/theme-next/theme-next-fancybox3 fancybox

```

注释：

[^1]: CN2-GIA线路由电信提供，国外到国内走的是电信的海底光缆。
[^2]: UDP协议是节点中，有 “[特]” 标识 的节点
[^3]: 使用了UDP传输协议的升级版KCP