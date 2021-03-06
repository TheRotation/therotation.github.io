---
title: Hexo个人博客域名绑定
date: 2019-03-12 13:40:00
tags: 个人博客
categories: Hexo博客搭建
description: 这是我用Github+Hexo框架搭建的个人博客，网上也有一堆教程，我在这里稍微总结整理一下，在此记录一下自己的搭建过程，当然我也会不定时更新自己踩过的坑~
---

# Hexo个人博客域名绑定

> 之前创建了基于Github+Hexo的个人博客，成功通过了本地测试和网络测试，已经可以通过 **username.github.io** 的网址进行联网访问，但终究还是与 **.com**、**.cn** 和 **.xyz** 等实际的域名有出入，也不利于个人博客的传播。现在我们就对个人博客的域名进行优化。

## 第一步：购买域名

这里我们以[阿里云](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&ved=2ahUKEwjw8q_RqtXtAhUOw4sBHfJAAlsQFjAAegQIBBAC&url=https%3A%2F%2Fcn.aliyun.com%2Findex.html&usg=AOvVaw0_c5t654-IiZam2FF6esA1)为例，当然我们也可以在腾讯云上购买。

1. 进入首页，搜索“域名注册”

   ![Qsoxn.png](https://b1.sbimg.org/file/chevereto-jia/2020/12/19/Qsoxn.png)

2. 自己想一个域名并查询是否已被占用

   ![Qs9gM.png](https://b1.sbimg.org/file/chevereto-jia/2020/12/19/Qs9gM.png)

3. 选择自己理想价位的域名购买即可，注意时间期限

   ![Qs6mh.png](https://b1.sbimg.org/file/chevereto-jia/2020/12/19/Qs6mh.png)

## 第二步：解析域名

1. 通过ping仓库名的形式获取IP地址

   ![QsPuk.png](https://b1.sbimg.org/file/chevereto-jia/2020/12/19/QsPuk.png)

2. 进入阿里云的“管理控制台“-”域名与网站“-”云解析DNS“，进入域名的解析设置，点击”新手指导“，**将得到的 IP 地址填到记录值一栏**，点击”确定“。

   ![QsQIR.png](https://b1.sbimg.org/file/chevereto-jia/2020/12/19/QsQIR.png)

   填完以后的解析列表会出现下图，解析域名成功

   ![QsDDj.png](https://b1.sbimg.org/file/chevereto-jia/2020/12/19/QsDDj.png)

## 第三步：域名绑定

1. 在本地 **blog\source** 文件下创建 **CNAME** 文件（无后缀名），在里面写上购买的域名并保存，例如：

   ![QsGZa.png](https://b1.sbimg.org/file/chevereto-jia/2020/12/19/QsGZa.png)

2. 最后到Github的 **username.github.io **项目库里点击Settings，填上新的域名

   ![QsBGI.png](https://b1.sbimg.org/file/chevereto-jia/2020/12/19/QsBGI.png)

   ![QsRzK.png](https://b1.sbimg.org/file/chevereto-jia/2020/12/19/QsRzK.png)

   



















