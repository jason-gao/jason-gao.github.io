---
title: hexo github pages 
date: 2019-07-07 18:04:41
tags:
    - hexo
    - node
categories:
    - node    
---

## 这东西能干啥？
- 搭建一个属于自己的blog
- 存放API文档
- ...

## 为什么要用这个？
- markdown语法让你专注于写自己的东西
- 丰富的插件和主题
- 自动化部署
- github pages可以存放静态文件，通过域名访问，这样不需要单独去买云主机，当然最好是自己买个，怎么玩都行

## 怎么用？
### 环境
- mac
    - MacBook Pro (Retina, 15-inch, Mid 2014)
    - 2.2 GHz Intel Core i7
    - 16 GB 1600 MHz DDR3
- node -v 
    - v12.3.1
- npm -v
    - 6.9.0

### 安装node
- Should be at least nodejs 6.9
- https://nodejs.org/zh-cn/

### 安装git
- https://git-scm.com/downloads     

### 安装 node hex-cli模块
- npm install -g hexo-cli

### 创建github 空项目
- 用自己用户名 例如：jason-gao.github.io，搭建好后可以通过这个域名直接访问，github pages自带的功能

### clone
- git clone git@github.com:jason-gao/jason-gao.github.io.git

### init
- 新建*source*分支存放hexo写作的源码，后面将public里的静态文件部署到*master*分支，通过jason-gao.github.io访问
    - git checkout -b source
- hexo init    

###  启动服务
- hexo server
- http://localhost:4000 访问预览可以看到效果

###  生成静态文件
- hexo g

### 部署到github pages
- 装hexo插件
    - npm install hexo-deployer-git --save
- 修改配置文件
```yaml
    deploy:
        type: git
        repo: git@github.com:jason-gao/jason-gao.github.io.git
        branch: master
```
- 部署
    - hexo d 此命令是将生成在public下的静态文件，推送到上面配置的仓库的对应分支

### 访问
- http://jason-gao.github.io 

### 自定义域名
- source文件夹下放置名为CNAME的文件，文件内容为gaolu.tech
- hexo g
- hexo d
- 域名解析商添加解析： blog CNAME jason-gao.github.io.
- http://gaolu.tech即可访问

