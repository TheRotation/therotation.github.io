---
title: Hexo博客同步管理及迁移
date: 2019-03-10 13:40:00
tags: 个人博客
categories: Hexo博客搭建
description: 这是我用Github+Hexo框架搭建的个人博客，网上也有一堆教程，我在这里稍微总结整理一下，在此记录一下自己的搭建过程，当然我也会不定时更新自己踩过的坑~
---

# Hexo博客同步管理及迁移

> 若仅用于发布新文章或修改网站样式文件时，只用重复第5步即可。
>
> 若涉及因更换/多开设备或重装系统导致的Hexo博客数据备份迁移，则需从第1步开始。

1. Github上创建或切换到 <span style="color:red">**hexo-blog分支**</span> (分支名随意)，然后在**hexo-blog分支所在仓库**的菜单栏**点击Setting**，进入后点击左侧栏的**Braches**菜单项，在Default branch中选择hexo-blog分支后即设置hexo-blog分支为<span style="color:red">**默认分支**</span> （原来是master）。

2. Github上切换到hexo-blog分支，接着克隆仓库到本地。

   ```
   git clone SSH密钥
   ```

3. 克隆后生成 **username.github.io文件夹** ，删除**除.git文件夹外**的其他文件夹。Windows默认隐藏，选择“我的电脑”工具栏“查看”，点击“选项”，再点击“查看”，勾上点选”显示/隐藏的文件、文件夹和驱动器“。

4. 复制克隆 **username.github.io文件夹** 中的 <span style="color:red">**.git文件夹**</span> 到本地备份的hexo项目根目录下，然后就可**删除**username.github.io文件夹

5. 在本地备份的hexo项目根目录下，依次执行以下提交命令：

   ```
   git add -A	或	git add .		  /*前者把工作区的变化提交到暂存区包括已删除的文件，后者不包括*/
   git commit -m "some description"
   git push origin hexo-blog		 /*推送到远程hexo-blog分支,此时Github的hexo-blog分支已刷新*/
   hexo g -d						                     /*发布网站并推送静态文件到master分支*/
   ```

   