---
title: Start With Hexo + github 遇到的问题
---


## 20170412 ##

使用Hexo + GitHub 搭建了个简易的博客……

## 记录一下踩过的坑…… ##

1. **Deployer not found: git**

	在终端执行命令：
		
		npm install hexo-deployer-git --save
	
	然后继续执行 **hexo deploye** 指令进行部署。 


2. **npm install时，出现npm error: RPC failed错误**

	npm是一个很好用的工具，全场是Node Packet Manager，是一个nodejs的包管理工具，但是美中不足的是当我们去安转包的时候却发现下载的速度太慢，但是没关系，还是有方法的就是利用淘宝的国内镜像，一下是[3个设置的方法](http://blog.csdn.net/zhy421202048/article/details/53490247 "3个设置的方法")：

	1.通过config命令
		npm config set registry https://registry.npm.taobao.org 
		npm info underscore （如果上面配置正确这个命令会有字符串response）

	2.命令行指定
		npm --registry https://registry.npm.taobao.org info underscore 

	3.编辑 ~/.npmrc 加入下面内容
		registry = https://registry.npm.taobao.org

3. **部署时保证README.md文件不被渲染**
	
	1. source目录下创建 README.md

	2. 配置文件\_config.yml中配置"skip_render"选项

			skip_render: README.md
