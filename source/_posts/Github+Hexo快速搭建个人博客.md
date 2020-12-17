---
title: Github+Hexo快速搭建个人博客
date: 2019-03-03 13:40:00
tags: 个人博客
categories: Hexo博客搭建
description: 这是我用Github+Hexo框架搭建的个人博客，网上也有一堆教程，我在这里稍微总结整理一下，在此记录一下自己的搭建过程，当然我也会不定时更新自己踩过的坑~
---

# Github+Hexo快速搭建个人博客

 

### 第一步：环境安装

1. <a href="http://nodejs.cn/download">下载安装Node.js</a>：安装完毕打开cmd命令行分别输入，显示版本号即为成功。

   ```
   node -v
   npm -v
   ```

2. <a href="https://git-scm.com/downloads">下载安装Git</a>：安装完毕后在桌面右击鼠标，当出现 Git GUI Here 和 Git Bash Here 即为成功。

   <br/>

### 第二步：新建Github项目库

1. <a href="https://github.com">注册Github</a>：确定用户名和邮箱，以后各种链接会建立在用户名和邮箱上，不建议修改。

2. 新建GitHub项目仓库：命名为 <span style="color:red">**用户名.github.io**</span>，勾选 **Initialize this repository with a README** 选项。创建完毕后就可用 **https://用户名.github.io** 访问到自己的博客。

   <br/>

### 第三步：Hexo框架安装与本地测试

1. 在合适的位置创建文件夹，文件夹名自定义，例如：在F盘下创建一个名为 blog 的文件夹。

2. 打开cmd命令行进入到bolg文件夹目录下。

3. 全局安装 Hexo 博客框架：

   ```
   npm install hexo-cli -g
   ```

4. 执行命令初始化 Hexo 博客框架：

   ```
   hexo init
   ```

5. 执行命令安装项目所需依赖包：

   ```
   npm install
   ```

6. 在blog文件夹中执行命令，自动在 **blog\source\\_posts** 文件夹下生成新的md格式博客文章。

   ```
   hexo new post '文章名'
   ```
   
7. 进入到 **blog\source\\_posts**目录查看新建的文章，编辑文本后保存。在blog文件夹下执行命令，用于开启本地服务器，成功开启后在浏览器中打开 **localhost:4000**，即可本地访问新创建的文章。

   ```
   hexo server
   ```

<br/>

### 第四步：配置主题

> 配置主题的步骤大致如下，配置步骤详情请看官网
>
> [Melody主题]( https://molunerfinn.com/hexo-theme-melody-doc/zh-Hans/ )
>
> [Butterfly主题](https://butterfly.js.org/posts/21cfbf15/#%E5%AE%89%E8%A3%9D)
>
> [Next主题](http://theme-next.iissnan.com/getting-started.html)

这里以Butterfly主题为例。(Butterfly主题是Melody的第三方魔改主题，基本语法一致)

因为网速问题，建议使用Git安装(Gitee)方式安装。

1. 打开cmd命令行进入到 bolg文件夹根目录下执行下列代码安装Butterfly主题：

   ```
   git clone -b master https://gitee.com/iamjerryw/hexo-theme-butterfly.git themes/butterfly
   ```

2. 安装辅助插件：

   bolg文件夹根目录下执行下列代码：

   ```
   npm install hexo-renderer-pug hexo-renderer-stylus --save
   ```

若想升级，则在blog/themes/butterfly主题目录下执行下列代码：

```
    git pull
```

为了减少升级主题后带来的不便，也可使用以下方法。

1. 此方法只支持 Hexo 5.0.0 以上版本，建议使用。如果已经在创建了 ，请删除掉**source/_data/butterfly.yml**
2. 将主题文件夹中的  **_config.yml** 复制到 blog根目录里，同时重新命名为 **_config.butterfly.yml**，以后只需要在 **_config.butterfly.yml** 进行配置就行。

Hexo会自动合并主题中的 **_config.yml** 和  **_config.butterfly.yml** 里的配置，如果存在同名配置，会使用 **_config.butterfly.yml** 的配置，其优先度较高。

<br/>

### 第五步：上传项目

> 要想将项目上传至 github 需要用 git 生成 SSH秘钥，通过 **SSH秘钥** 方可将本地项目和 github 联系起来，具体步骤如下：

1. 首先桌面右击鼠标打开 **Git Bash Here** 。

2. 执行如下命令设置你的用户名和邮箱，内容请自行替换。

   ```
   git config --global user.name "Github用户名"
   git config --global user.email "Github绑定邮箱"
   ```

3. 上传文件需要配置SSH Key，不然无法上传，需要先查看本地是否含有SSH密钥，若含有，则需要将本地的密钥删除。输入代码检查本地SSH密钥。

   ```
   ls -al ~/.ssh
   ```

4. 生成SSH密钥（直接按回车）：（秘钥默认生成存储路径是：**C:\Users\Administrator.ssh**）

   ```
   ssh-keygen -t rsa -C "Github绑定邮箱"
   ```

5. 查看生成的SSH密钥，并复制。

   ```
   cat ~/.ssh/id_rsa.pub
   ```

6. 登录 github 进入头像下的 **settings** 中点击 **SSH and GPG keys** 选项。

7. 点击 **New SSH key** 添加 SSH秘钥, title 任意取 ，将<span style="color:red">**SSH秘钥**</span>粘贴到 Key 中并保存。

8. 输入代码，若回复你的用户名则绑定成功。

   ```
   ssh -T git@github.com
   ```

9. 接着进入到自己的仓库点击绿色按钮 **Clone or download** 选择 **Use SSH** 复制地址。

10. 打开blog文件夹下的配置文件**_config.yml**找到 **deploy**，粘贴SSH密钥到**repository**属性处（没有则自建，注意.yml文本格式）。

11. 若想生成和部署文章到GitHub，还需要执行命令安装扩展。

    ```
    npm install hexo-deployer-git --save
    ```

12. 最后在blog文件夹中分别执行，就可以生成静态页面部署到GitHub了，打开 **用户名.github.io** 即可联网访问。

    ```
    hexo clean
    hexo d -g
    ```

    <br/>








