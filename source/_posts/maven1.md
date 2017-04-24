---
title: maven学习笔记01--github创建项目，拉取到本地转换成maven项目 
date: 
top: 0 #整数，越大越靠前
tags: [maven]
categories: [maven]
description:
---
1.start a project
2.Repository name根据自己喜好取
3.开源的就先public，否则选择private（根据自己需求选择）
4.add .gitignore选择maven
5.add a license 啥协议，随便选吧
6.add a readme,写点自己项目的记录文档（markdown格式）
7.clone or download，复制项目clone地址
8.打开idea，VCS--->checkout from.....--->github--->在url栏粘贴刚才复制的地址--->create project...--->一直选择next--->finish--->选择现有窗口打开项目还是新窗口打开项目
9.至此已经成功clone github项目至本地仓库
10.拷贝一个pom.xml文件至项目根目录下（与readme同级）
11.在pom.xml文件中添加groupId，artifactId，version，packaging
&nbsp;&nbsp;&nbsp;&nbsp;1）groupId定义了项目属于哪个组（建议命名为包路径前缀，例如，如果你的公司是mycom，有一个组是mygroup，此项目属于mygroup，那么groupId就应该是com.mycom.mygroup）
&nbsp;&nbsp;&nbsp;&nbsp;2）artifactId定义了当前maven模块在项目中唯一的ID（建议命名为项目名-模块名,例如，若项目名是myapp，模块名为sdk，则artifactId可以为myapp-sdk）
&nbsp;&nbsp;&nbsp;&nbsp;3）version按个人需求定义版本，SNAPSHOT意为快照，说明该项目还处于开发中，是不稳定的版本.
&nbsp;&nbsp;&nbsp;&nbsp;4）packaging定义项目产生的构件类型，例如jar、war、ear、pom。插件可以创建他们自己的构件类型，所以前面列的不是全部构件类型
12.右键pom.xml选择add as maven project--->ignore....
13.右键项目，new--->module--->maven--->create from ....--->next
14.此时只需要在输入artifactId和module name就可以了。