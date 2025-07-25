---
counter: True
---

# 校园网连接指南

!!! Warning
    该页面正在施工ing

    由于 ZJU 正在搞 aTrust 逐步取代之前的 EasyConnect，原来的 RVPN (ZJU Connect) 禁用了大量端口，本页内容需要一定修改。这里暂时指路学爷组 xg 的 [docker 部署 atrust 方法](https://note.tonycrane.cc/web/devops/tunnel/#zju-connect). 现阶段来说，使用 WebVPN 应该就够用了，感兴趣的同学可以阅读有关 RVPN 的内容。

!!! Note "序言"
    - 校园网是必需的，在办理好校园网后，才可以使用浙大里的无线网以及访问浙大校内资源。
    - 校园网需要先激活再缴费（第一个月可以不用缴费）。在校外可以选择 WebVPN 或 aTrust 连接访问校内资源，进入校园后可以采用无线等方式更便捷的连接校网。其中，使用无线网及 WebVPN 就足以满足一定的需求了。
    - 本文中提到的网络密码不一定和浙江大学统一身份认证所用密码相同，在具体使用时还请注意。

## 激活及缴费

!!! Warning "注意"
    第一个月的校网是免费的，不需要充值，但是**一定要激活**。

### 激活

进入网站 [myvpn.zju.edu.cn](https://myvpn.zju.edu.cn/) 或者通过浙大钉—工作台—全部—网络缴费进入信息技术中心网站，这里将浙大钉换为钉钉也可以。

!!! Note "网页版激活界面"
    <figure markdown="1">![](images/activate.png)</figure>

第一次使用 VPN 之前先要激活账号，点击“激活账号”可跳转到浙江大学统一身份认证并激活（可能会用到校园卡密码，身份证后六位）。

!!! Warning "注意"
    钉钉校园卡分别有卡号和学号两项，其中学号是名字右侧 325 开头的十位数字，本文中要用到的只有学号.

### 缴费

成功激活后，回到 [myvpn.zju.edu.cn](https://myvpn.zju.edu.cn/)，输入 VPN 用户名（即学号）和密码并进行缴费。

套餐一共有三种，其费用及对应带宽见下面表格，不过由于校园网络存在升级，具体数据仅供参考。

|费用（元 / 月）|带宽（Mbps）|
|:---:|:---:|
| 10 | 10 |
| 30 | 50 |
| 50 | 100|

个人感觉 **10 元/月** 已经足够日常使用了。 

办理了学校杭州移动或电信电话卡的同学可以免费升级一个价位的套餐，购买了电话卡且想要升级的需持身份证前往相应营业厅办理。 

## 校外连接

校外连接方式主要有 WebVPN 和 RVPN 两种。

### WebVPN

WebVPN 是一种通过网页跳转来实现外网访问内网的连接方式，因此无需安装软件即可访问内网资源。

首先进入 [webvpn.zju.edu.cn](https://webvpn.zju.edu.cn/)，可以看到以下界面，然后输入用户名及网络密码并登录，这里的网络密码可能与统一身份认证密码不同。

<figure markdown="1">![](images/WebVPN-1.png)</figure>

成功登录后，在以下界面红框所圈的搜索框输入要访问的学校网址即可。（例如 [cc98.org](https://www.cc98.org/)）

<figure markdown="1">![](images/WebVPN-2.png)</figure>


### RVPN

**aTrust** 是新版的 RVPN，根据[官网](https://zuits.zju.edu.cn/_t2014/2021/0615/c49798a2395843/page.psp)上的信息：“2025年5月19日起，RVPN系统不再支持SSH、远程桌面、Telnet、FTP等非Web类协议。如需使用相关服务，请通过新版RVPN系统访问。”因此可以参考[官网给出的教程](https://zuits.zju.edu.cn/_upload/article/files/4c/f2/dce9497346f385227e317912d3e0/385076f5-0101-4797-ba37-8a8b388aea31.pdf)尝试使用 aTrust。

> **ZJU Connect** 是**比较推荐**的一种校外连接方式，相较于官方推荐的 aTrust 以及之前的 EasyConnect 有很多好处。但是由于其基于旧的 RVPN 架构，在 EasyConnect 被淘汰、aTrust 上新之后 ZJU Connect 暂时处于“被 ban 掉”的状态。不过最近该项目对于新 RVPN 的适配做出了一定突破（处于测试阶段），感兴趣的同学可以阅读相关的[帖子](https://www.cc98.org/topic/6214942)与 [issue](https://github.com/Mythologyli/zju-connect/issues/75).

## 校内连接

### 无线连接

校园内的 Wi-Fi 网络基本可以覆盖到日常学习生活的大部分区域，主要有 ZJUWLAN、ZJUWLAN-Secure。

ZJUWLAN 在 Wi-Fi 里可以直接找到并连接，但是需要认证，一般在连接后会弹出认证窗口，在填写好用户名、密码后，即可正常上网。一次认证有效时长为 14 天，到期后需要重新认证。

!!! Note "网页版认证界面"
    <figure markdown="1">![](images/net3_zju.png)</figure>

如果没有弹出的话也可以直接访问 [net3.zju.edu.cn](http://net3.zju.edu.cn)，进入认证界面。

ZJUWLAN-Secure 在连接时，在输入所用的用户名、密码后即可完成连接，下面简要介绍 Windows 以及 Android 系统上的操作。

=== "Windows"
    点击桌面右下方菜单栏中的无线网图标，选择 ZJUWLAN-Secure 进行连接，在输入用户名及密码后，点击连接后即可上网。
    ???+ General "操作步骤"
        === "Step 1"
            <figure markdown="1">![](images/ZJUWLAN-Secure-Windows-1.png)</figure>
        === "Step 2"
            <figure markdown="1">![](images/ZJUWLAN-Secure-Windows-2.png)</figure>
        === "Step 3"
            <figure markdown="1">![](images/ZJUWLAN-Secure-Windows-3.png)</figure>
        === "Step 4"
            <figure markdown="1">![](images/ZJUWLAN-Secure-Windows-4.png)</figure>

=== "Android"
    在手机中进入 WLAN 连接页面，选择 ZJUWLAN-Secure 进行连接，之后的阶段 2 身份认证和 CA 证书均选择**不认证**，在输入用户名和密码后，点击连接即可。
    ???+ General "操作步骤"
        === "Step 1"
            <figure markdown="1">![](images/ZJUWLAN-Secure-Android-1.jpg)</figure>
        === "Step 2"
            <figure markdown="1">![](images/ZJUWLAN-Secure-Android-2.jpg)</figure>

### 有线连接

不太推荐使用有线连接，个人感觉浙大的有线网络并不比无线网络快，而且很不稳定，并且会和其他代理产生冲突，所以很麻烦，不建议使用。

若还是有需求，可以参考[如何在寝室用有线上网呢](assets/如何在寝室用有线上网呢.pdf)。

!!! Warning "特殊情况"
    连接校园网后可能遇到的小问题：如果连接校园网后发现可以正常登录 QQ，但是无法打开网页的情况可参考[这篇文章](https://mp.weixin.qq.com/s?mid=2649491759&sn=265e8378ad15aa5536c17c87c4e75272&idx=1&__biz=MjM5OTk0NTg3Mg==)进行修复。
