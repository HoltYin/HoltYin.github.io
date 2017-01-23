---
title: github利用hexo搭建博客
tags: [hexo]
categories: hexo
top: 10
---
### 下载并安装node.js
   安装完毕后，可以在dos控制台输入node -v查看版本号。
### 下载git
   这里与远程github间最好是SSH加密方式，不懂的同学参考。[git命令小结](http://note.youdao.com/)
### 安装hexo
   在dos控制台npm install -g hexo-cli
### 初始化hexo
   1.在某个你指定的目录下打开dos控制台（可以先进入目录，然后在顶部输入cmd）
   <img src="/images/hexo/hexo1.jpg" >
   2.输入命令hexo init 文件名（我的是文件名是blog）
### 拉取远程blog项目
   1.在github上新建一个仓库
   2.从github上将新建的仓库拉到idea上（我使用的工具是idea，这里假设拉取到工作目录的文件名是remoteblog）
   
### 在本地仓库中引入hexo
   1.将前面init的blog目录中的东西全部copy到remoteblog目录中
   2.在remoteblog目录下的dos控制台输入命令npm install,下载package.json中的依赖
### 本地启动hexo
   1.改一下本地blog项目下_config.yml文件中的配置，可以参考网上的配置，百度一下，一大片
   2.在remoteblog目录下的dos控制台输入命令 hexo clean
   3.hexo g
   4.hexo s -p 5000
   5.在浏览器输入localhost:5000就可以访问你的本地blog了
### 部署到github
   1.在remoteblog目录下的dos控制台输入命令 hexo clean
   2.hexo g
   3.hexo d
   
   
   **到此就可以去你的github上访问的你的博客了。一般地址是https://加上
   <img src="/images/hexo/hexo2.jpg" >**
   