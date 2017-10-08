---
title: 搭建hexo博客
date: 2017-10-07 22:00:38
tags:
---

终于有时间给自己搭建博客，总结一番~

#### 1.技术选型  ####
三种方案：wordPress,hexo,自己撸个博客
wordPress:以前玩过，但是有点重，需要独立的服务器，需要数据库，优点：写东西方便，有数据库好备份。

hexo:基于node,说白了就是写好模板主题，用node生成静态页面然后部署到服务器上，缺点：比较麻烦，数据不好管理，写博文麻烦，我估计发布的博文多了会很吃内存，因为全部是静态页面；优点：不需要数据库，服务器可以用github,coding的Pages服务，很轻量，也很灵活。

自己撸：其实一直很想基于node-koa-mongdb，前后端一起写，自己撸个博客，好好练练自己的node在服务端的不足，如果做全注册，登录，评论，分类，标签，加上UI（我能看出美的东西，要求也很高，可我自己不会设计o(╯□╰)o）工程量还是有点大的。。不撸个1个月，估计很难撸出自己满意的东东，心有余，时不足。

自己的node感觉不过关，喜欢和node有关的一切~最终选择了hexo,选择了next主题，做了一键部署，熟悉了markDownmaD语法后，发布博文也很快，感觉也蛮不错的~
<!--more-->
### 2.搭建流程及常用命令 ###
安装node环境
新建myHexo文件夹
全局安装hex-cli，hexo,
进入myHexo目录，执行hexo init
执行npm install
``` bash
$ npm install hexo-cli -g
$ npm install hexo -g
$ cd myhexo
$ hexo init
$ npm install
```
![](http://oxguwnk9i.bkt.clouddn.com/imgcut1.png)
然后就可以参考[hexo官方文档](https://hexo.io/zh-cn/docs/)和[next主题官方教程](http://theme-next.iissnan.com/getting-started.html) 修改各种配置，菜单、
执行hexo g,hexo s，在本地先跑起来
``` bash
$ hexo clean //清楚之前生成的静态文件
$ hexo g //生成新的静态文件
$ hexo s //启动本地服务
```
最后就是部署到github或者coding上，2个都部署也可以，详细方法点[这里](http://blog.csdn.net/u011303443/article/details/51509351)

注：一定要安装 hexo-deployer-git，否则hexo d命令会报错
``` bash
$ npm install hexo-deployer-git --save-dev //hexo部署插件
$ hexo d //生成静态文件并部署到指定环境
```
如果配置无误，hexo d命令执行完毕后 控制台会打印出INFO Deploy done:git,这说明部署成功，访问自己项目PagesUrl就能够看见自己的博客了