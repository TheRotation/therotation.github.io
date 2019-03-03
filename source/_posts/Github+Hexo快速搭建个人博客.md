---
title: Github+Hexo快速搭建个人博客
date: 2019-03-03
tags: 个人博客
categories: Hexo

---

{% note info %} **1、Node.js安装：**{% endnote %}<br/>　　下载安装Node.js，安装完毕打开cmd命令行分别输入node -v、npm -v，显示版本号即为成功。
<br/>　　**[下载Node.js](http://nodejs.cn/download/)**<br/>
{% note info %} **2、Git安装：**{% endnote %}<br/>　　下载安装git，安装完毕后在桌面右击鼠标当你看到 Git GUI Here 和 Git Bash Here 即为成功。
<br/>　　**[下载Git](https://git-scm.com/downloads)**<br/>
{% note info %} **3、注册Github账号：**{% endnote %}<br/>　　注册时，用户名和邮箱是常用的，需要以后各种链接都会建立在用户名和邮箱上，所以确定好后尽量不要修改。
<br/>　　**[注册Github](https://github.com/)**<br/>
{% note info %} **4、新建项目库：**{% endnote %}<br/>　　在GitHub新建仓库时，仓库命名为：<span style="color:red">**用户名.github.io**</span>，
勾选 **Initialize this repository with a README** 选项。创建完毕后，你就可以用  ``https://用户名.github.io``  访问到自己的博客。<br/>
{% note info %} **5、Hexo安装：**{% endnote %}<br/>　　1）在合适的位置创建一个文件夹，例如：在F盘下创建一个名为 <span style="color:red">blog</span> 的文件夹。blog可以自定义,若你使用了别的名字，下文出现的 blog 请自行替换。
<br/>　　2）打开cmd命令行进入到 <span style="color:red">bolg文件夹</span> 目录下。
<br/>　　3）然后在命令行里输入 <span style="color:red">``npm install hexo-cli -g``</span>，全局安装 Hexo 。
<br/>　　4）执行 <span style="color:red">``hexo init``</span> 命令初始化你的 Hexo 博客。
<br/>　　5）执行 <span style="color:red">``npm install``</span> 命令安装项目所需依赖包。
<br/>　　6）执行 <span style="color:red">``hexo server``</span> 命令，开启本地服务器。
<br/>　　7）开启本地服务器成功后在浏览器中打开 <span style="color:red">``localhost:4000``</span>，即可访问。<br/>
{% note info %} **6、将项目上传至github：**{% endnote %}<br/>　要想将项目上传至 github 需要用 git 生成 ssh秘钥，通过 ssh秘钥 方可将本地项目和 github 联系起来，具体步骤如下：
<br/>　　1）首先桌面右击鼠标打开 Git Bash Here 。
<br/>　　2）执行如下命令设置你的用户名和邮箱，内容请自行替换。
<br/>　　　　<span style="color:red">``git config --global user.name "Github用户名"``</span>
<br/>　　　　<span style="color:red">``git config --global user.email "Github绑定邮箱"``</span>
<br/>　　3）上传文件需要配置SSH Key，不然无法上传，需要先查看本地是否含有SSH密钥，若含有，则需要将本地的密钥删除。输入 <span style="color:red">``ls -al ~/.ssh``</span> 检查本地SSH密钥。
<br/>　　4）生成SSH密钥（直接按回车）：<span style="color:red">``ssh-keygen -t rsa -C "Github绑定邮箱"``</span>，秘钥默认生成存储路径是：<span style="color:red">``C:\Users\Administrator\.ssh``</span>
<br/>　　5）利用 <span style="color:red">``cat ~/.ssh/id_rsa.pub``</span> 查看生成的SSH密钥，并复制。
<br/>　　6）登录 github 进入头像下的 **settings** 中点击 **SSH and GPG keys** 选项。
<br/>　　7）点击 **New SSH key** 添加 SSH秘钥, title 任意取 ，将 SSH秘钥粘贴到 Key 中并保存。
<br/>　　8）输入 <span style="color:red">``ssh -T git@github.com``</span>，若回复你的用户名则绑定成功。
<br/>　　9）接着进入到你的仓库点击绿色按钮 **Clone or download** 选择 **Use SSH** 复制地址。
<br/>　　10）打开blog文件夹下的配置文件_config.yml找到 **deploy**，粘贴SSH密钥到repository属性处。
<br/>　　11）在blog文件夹中执行 <span style="color:red">``hexo new post '文章名'``</span> 命令，自动在 blog\source\_posts 文件夹下生成新的md格式博客文章。
<br/>　　12）进入到 blog\source\_posts目录就能看到你创建的文章，打开在虚线下面写点内容。
<br/>　　13）在blog文件夹下执行 <span style="color:red">``hexo server``</span> 就可以访问 <span style="color:red">``http:localhost:4000``</span> 本地博客看到刚刚创建的文章了。
<br/>　　14）若想生成和部署文章到GitHub，还需要执行 <span style="color:red">``npm install hexo-deployer-git --save``</span> 命令安装扩展。
<br/>　　15）最后在blog文件夹中执行 <span style="color:red">``hexo clean``</span>和<span style="color:red">``hexo d -g``</span> 就可以生成部署到GitHub了，打开 <span style="color:red">``用户名.github.io``</span> 即可联网访问。<br/>
{% note info %} **7、更换主题：**{% endnote %}<br/>　　详细步骤请看：
<br/>　　**[NEXT主题官网](http://theme-next.iissnan.com/getting-started.html)**
<br/>　　**[NEXT主题其他炫酷设置1](https://www.jianshu.com/p/f054333ac9e6)**
<br/>　　**[NEXT主题其他炫酷设置2](https://zhuanlan.zhihu.com/p/30836436)**
<br/>　　**[NEXT主题添加背景图片](https://blog.csdn.net/wang631106979/article/details/51375184)**
<br/>　　**[NexT主题添加点击爱心效果](https://asdfv1929.github.io/2018/01/26/click-love/)**
<br/>　　**[Hexo博客美化添加live2d萌物](https://asdfv1929.github.io/2018/01/26/click-love/)**<br/>
{% note info %} **8、如何将修改后的hexo博客同步到Github，而不是只在本地有效显示：：**{% endnote %}<br/>　　1）github上创建或切换到hexo-blog分支(分支名随意)，然后设置hexo-blog分支为<span style="color:red">默认分支</span>(原来是master)：
<br/>　　在hexo-blog分支所在仓库的菜单栏点击Setting，进入后点击左侧栏的Braches菜单项，在Default branch中选择hexo-blog分支即可。
<br/>　　接着<span style="color:red">``git clone``</span>仓库到本地。
<br/>　　2）此时本地会多出一个<span style="color:red">username.github.io文件夹</span>，命令行cd进去，删除<span style="color:red">除.git文件夹外</span>的其他文件夹。（如果你看不到这个文件夹，说明是隐藏了。windows下需要右击文件夹内空白处，点选'显示/隐藏 异常文件'，Mac下我就不知道了）
<br/>　　3）命令行 <span style="color:red">``git add -A``</span> 把工作区的变化（包括已删除的文件）提交到暂存区（ps: <span style="color:red">``git add .``</span> 提交的变化不包括已删除的文件）。
<br/>　　4）命令行 <span style="color:red">``git commit -m "some description"``</span> 提交。
<br/>　　5）命令行 <span style="color:red">``git push origin hexo-blog``</span> 推送到远程hexo-blog分支。此时刷下github，如果正常操作，hexo-blog分支应该已经被清空了。
<br/>　　6）复制本地<span style="color:red">username.github.io文件夹</span>中的<span style="color:red">.git文件夹</span>到hexo项目根目录下。此时，hexo项目已经变成了和远程hexo-blog分支关联的本地仓库了。而username.github.io文件夹的使命到此为止，你可以把它删掉，因为我们只是把它作为一个“中转站”的角色。
<br/>　　7）以后每次发布新文章或修改网站样式文件时，<span style="color:red">``git add .``</span> & <span style="color:red">``git commit -m "some description"``</span> & <span style="color:red">``git push origin hexo-blog``</span> 即可把环境文件推送到hexo-blog分支。然后再 <span style="color:red">``hexo g -d``</span> 发布网站并推送静态文件到master分支。












