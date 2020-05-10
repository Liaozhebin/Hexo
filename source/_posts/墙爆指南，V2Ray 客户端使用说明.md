---
title: 墙爆指南，V2Ray 客户端使用说明
date: 2020-02-02 
updated: 2020-05-03 
urlname: BreakWall_V2Ray_User_Guide
tags:
  - 科学上网
  - BreakWall
  - V2Ray
categories: 
  - 科学上网
  - V2Ray
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
本文介绍如何在 Android、IOS、PC 客户端中使用 **V2Ray** ,包含： 如何使用`Vmess`链接导入节点，如何完成基础设置并开始使用。 
<!---more--->

## 目录
* [自助工具放前头](#%E8%87%AA%E5%8A%A9%E5%B7%A5%E5%85%B7%E6%94%BE%E5%89%8D%E5%A4%B4)
* [如何导入节点 (添加节点说明)](#如何导入节点-添加节点说明)
  * [从剪切板导入](#%E4%BB%8E%E5%89%AA%E5%88%87%E6%9D%BF%E5%AF%BC%E5%85%A5)
* [客户端使用说明](#%E5%AE%A2%E6%88%B7%E7%AB%AF%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E)
  * [Android 客户端](#Android-客户端)
  * [IOS 客户端](#IOS-客户端)
  * [PC 客户端](#PC-客户端)
    * [\*PC 杀毒安全软件问题](#PC-杀毒安全软件问题)
    * [PC 客户端说明正文](#PC-杀毒安全软件问题)
  * [Q&amp;A PC 客户端存在的问题](#Q-A-PC-客户端存在的问题)
* [如何选择合适的节点](#%E5%A6%82%E4%BD%95%E9%80%89%E6%8B%A9%E5%90%88%E9%80%82%E7%9A%84%E8%8A%82%E7%82%B9)
  * [等级划分](#%E7%AD%89%E7%BA%A7%E5%88%92%E5%88%86)
  * [运营商标识](#%E8%BF%90%E8%90%A5%E5%95%86%E6%A0%87%E8%AF%86)
  * [节点名称标识含义](#%E8%8A%82%E7%82%B9%E5%90%8D%E7%A7%B0%E6%A0%87%E8%AF%86%E5%90%AB%E4%B9%89)

## 自助工具放前头

1. [查询宽带网络运营商](https://www.ipip.net/ip.html)

2. [查询国外网站可访问情况](https://ip.skk.moe/)；[备用站点](http://ip111.cn)

  **临时链接**


## *如何导入节点 (添加节点说明)

> 因V2Ray设置较复杂，如无特殊情况，统一从采用 `从剪切板导入`  的方式批量添加节点

### 从剪切板导入
复制一大长串你看不懂的 “有序字符”，然后点击从剪切板导入即可一次性添加所有节点信息
> “有序字符”，长下面这个样子，仅仅是举例，可以尝试导入，但不是有效节点。
><small>vmess://ew0KICAidiI6ICIyIiwNCiAgInBzIjogInYycmF55paw5Yqg5Z2hTmV0ZmxpeC1jbG9uZSIsDQogICJhZGQiOiAic2cudGlrdG9rLnBhZ2UiLA0KICAicG9ydCI6ICI0NDMiLA0KICAiaWQiOiAiODk2M2Y1ZDgtZTRkYy0zMzY4LTk0NmQtZGYwN2UyMDc4M2M5IiwNCiAgImFpZCI6ICIxNiIsDQogICJuZXQiOiAid3MiLA0KICAidHlwZSI6ICJub25lIiwNCiAgImhvc3QiOiAic2cudGlrdG9rLnBhZ2UiLA0KICAicGF0aCI6ICIvdjJyYXkiLA0KICAidGxzIjogInRscyINCn0= </small>



## *客户端使用说明 

### Android 客户端

安卓客户端分成2张图进行说明，分别为`主界面`和`设置界面`

> 1. 确保手机时间为北京时间 
> 2. 导入节点
> 3. 修改设置 (参考设置界面图)
> 4. 测试`全部配置真连接`，根据结果选择合适的节点
> 5. enjoy it ...

【主界面图】：

> ![安卓主界面.png](https://i.loli.net/2020/02/03/ZV7suntNBI4OeFr.png)

【设置界面】：

> ![安卓设置页.png](https://i.loli.net/2020/02/02/CVq67BwTGcXtymf.png)



### IOS-客户端

仅用文字进行说明：

> 1. 确保手机时间为北京时间 
> 2. 打开 `ShadowRocket APP` 复制导入节点
> 3. 点击右上角的 `开关`  开启
> 4. enjoy it ...



### PC 客户端

#### \*PC 杀毒安全软件问题

条件允许的话，还请大家尽量不要使用 `360软件（含浏览器）`，下面推荐一些更好的 `免费安全软件`：

浏览器的话：强推 `Chrome` 次选 `firefox` `微软edge` `Opera`

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

#### PC 客户端说明正文

PC客户端使用 `右下角托盘` 和 `主界面` 图进行说明：

> 1. 确保手机时间为 `北京时间`
> 2. 解压压缩包
> 3. 打开文件夹里的 `v2rayN.exe`
> 4. 看 `右下角托盘图` 进行设置，
>    1. 先添加节点  ` 从剪切板导入URL节点  ` 
>    2. 选择 `服务器节点` 并选择 `PAC代理` 模式`
> 5. 其他更多操作参考主界面图 `服务器速度测试` && `服务器延迟测试` 
> 6. enjoy it ...

【主界面图】：

> ![PC-主界面解释.png](https://i.loli.net/2020/02/03/GDrT3aVQYxnqN2F.png)

【右下角托盘图】：

> ![PC-托盘解释.png](https://i.loli.net/2020/02/02/XoshcCP5iOAnrRt.png)



### Q&A PC 客户端存在的问题

个人测试发现，PC客户端似乎存在一定的不稳定性：

- 频繁切换节点会导致上一个节点再也无法连接上，需要关闭客户端重新打开，甚至重启电脑





## 如何选择合适的节点

### 等级划分

- **S > A+ > A > A- > B+ > B > B- > C+ > C** 

  > 注意：不绝对，只是引导作用，一般情况下都可以按等级标识来使用，连接效果不好时换节点类型试试

### 运营商标识

- [电] = 电信；[移] = 移动；[联] = 联通

### 节点名称标识含义

- **禁：** 
  
  - **高级节点，严禁滥用；严禁走代理下载大文件(3GB)；禁止看2K(不含)以上视频（特别是移动S级节点)**
  
- **转**：
  
  - 表示`中转服务器`，使用国内借道中转<电信or联通>的方式给移动加速   example：`04转02`  表示   `使用中转方式使用02节点`
  
- **数字**：

  - 服务器编号标识，数字一样代表服务器一样

  

- ~~**特**[^3]：~~
  
- ~~使用了特别的网络协议，可使网络质量提升一个等级(example：[B-] 变为 [A-])，**值得一试（特别是移动用户**（部分地区运营商无效，电信联通在网络不好的时候也可以试试）~~  
  
  

------



<details><summary> 点击展开内容 </summary> 

## (爱看不看）对移动网络的小吐槽

一直知道移动的出国环境不太好，每次升级节点都因此搞到头疼（想着如何改善一下）

移动不好用，用的人还挺多，搞不懂（似乎也没便宜多少，也就宽带便宜甚至免费）

这次使用了最高等级的`CN2-GIA线路`[^1]和特别的`UDP协议`[^2]，不知道改善如何，` 01节点 ` 使用下来，感觉还不错的话，后期可以考虑增加一个 `01` 节点类型的服务器，同时，吐槽移动的出国流量是真滴贵，`01` 节点流量达 `0.25元/GB`，请移动的且用且珍惜。

反观联通和电信：就这次的节点服务器，都是可以用的很舒服的了。

`2020年2月2日 Up to date`




**不过移动会这样还是有他自己的现实原因的：**

> 便宜(一分钱一分货) + 用户**巨**多（中国第一用户保有量，最低海底光缆拥有者，出国海底光缆承载量有限，人均少）
>
> 随便引用一篇知乎的片段：[原文：中国大陆目前国际网络的建设状况](https://zhuanlan.zhihu.com/p/64467370)
>
> ![吐槽.png](https://i.loli.net/2020/02/02/VeTWI5rhB1tYqMo.png)



### 把吐槽浓缩成一句话

**总的来说，就是想跟所处移动环境的你们，有条件的话，尽量还是选择联通或者电信网络吧....**
</details>

## 注释

[^1]: CN2-GIA线路由电信提供，国外到国内走的是电信的海底光缆。
[^2]:UDP协议是节点中，有 “[特]” 标识 的节点
[^3]: 使用了UDP传输协议的升级版KCP