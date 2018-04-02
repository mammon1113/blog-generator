---
title: 建立hexo
---
之前用过一次hexo，不过当时没弄妥帖，以至于后续一直在用简书写。现在从新弄弄。
使用 Hexo + GitHub 是可以轻松搞出一个好看的博客的，以下是步骤。

====================================================
## 基础配置
1.在 GitHub 上新建一个空 repo，repo 名称是「你的用户名.github.io」（请将你的用户名替换成真正的用户名）
2.npm install -g hexo-cli，安装 Hexo
3.hexo init myBlog

步骤3很像git里面的init

4.cd myBlog
5.npm i

以上步骤均是在配置环境

6.hexo new 博文标题，你会看到一个 md 文件的路径

这里可以简写成hexo n

7.start xxx.md，编辑这个 md 文件

此时文章已经生成，但是本地还没有index文件用来加载md文章

8.start _config.yml，编辑网站配置
1.1把第 6 行的 title 改成你想要的名字
1.2把第 9 行的 author 改成你的大名
1.3把最后一行的 type 改成 git(type: git)
1.4在最后一行，与 type 平齐，加上一行 repo: 仓库地址 （请将仓库地址改为「你的用户名.github.io」对应的仓库地址

该步骤很重要，如果你想用github加载你的hexo。这个文件包含了很多信息，可以用于修改。

9.npm install hexo-deployer-git –save，安装 git 部署插件
10.hexo deploy
11.进入「你的用户名.github.io」对应的 repo，打开 GitHub Pages 功能，如果已经打开了，就直接点击预览链接
12.你现在应该看到了你的博客！

====================================================
## 配置主题
1.https://github.com/hexojs/hexo/wiki/Themes 上面有主题合集
2.随便找一个主题，进入主题的 GitHub 首页，比如我找的是 https://github.com/iissnan/hexo-theme-next
3.复制它的 SSH 地址或 HTTPS 地址，假设地址为 git@github.com:iissnan/hexo-theme-next.git
4.cd themes
5.git clone git@github.com:iissnan/hexo-theme-next.git
6.cd ..
7.将 _config.yml 的第 75 行改为 theme: hexo-theme-next，保存
8.hexo generate
9.hexo deploy
等一分钟，然后刷新你的博客页面，你会看到一个新的外观。如果不喜欢这个主题，就回到第 1 步，重选一个主题。


====================================================
## 上传源代码
注意「你的用户名.github.io」上保存的只是你的博客，并没有保存「生成博客的程序代码」，你需要再创建一个名为 blog-generator 的空仓库，用来保存 myBlog 里面的「生成博客的程序代码」。
1.在 GitHub 创建 blog-generator 空仓库
2.将myBlog上传即可
3.以后换电脑，直接push这个仓库，在配置环境安装hexo，就可以继续使用了。

====================================================
另外对这次建立hexo做个小总结~

# 建hexo的文章其实只需要四步：
(1)hexo n
(2)找到.md文件进行写作
(3)hexo g
(4)hexo d

n、g、d 分别代表 新建md文件、生成静态index本地页面、发布

# 修改文章只需要三步：
(1)修改你的本地文章.md
(2)hexo g
(3)hexo d

