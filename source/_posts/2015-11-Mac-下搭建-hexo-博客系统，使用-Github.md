title: Mac  下搭建 hexo 博客系统，使用 Github
date: 2015-11-13 14:41:47
categories: hexo
tags: [hexo, Mac, blog]
---

之前用 Octopress 搭建了 blog，这次迁移到 hexo 上，随便写点东西记录一下。

<!-- more -->

## Github Pages

这个其实是第一步啦，Mac 是自带 Git 的，不过版本可能不高，有必要可以升级下。

关于配置 Github SSH 以及 Github Pages 的创建因为之前已经做过了，就不再做介绍了，网上文章很多，随手一搜就好。

## Homebrew 

这可是个神器，Mac 下安装各种应用特别舒服。我们主要用它来安装 node.js。

如果你的 homebrew 是之前很久安装的，可能需要升级一下，因为 OS X EL Capitan 弄了很多权限之类的东西。

```shell
// 升级 homebrew
brew update
```

## Node.js

HomeBrew 安装好了之后，直接安装 node

```shell
// 安装 node
brew install node
```

如果安装的过程中，出现了错误。应该就是 OS X EL Capitan 的问题，SIP 机制不允许对 /usr 目录做修改。尝试使用一下命令解决：

```shell
sudo chown -R $(whoami):admin /usr/local
```

如果还是没有解决，去 homebrew 的文档页面中详细查询：[homebrew OS X 10.11](https://github.com/Homebrew/homebrew/blob/master/share/doc/homebrew/El_Capitan_and_Homebrew.md)



## Hexo

使用 npm 安装

```shell
npm install -g hexo
```

### 初始化 hexo

新建一个目录作为 hexo 博客的存放地点，我选择了建立在用户主目录下：

```shell
cd ~
mkdir hexo
cd hexo
hexo init
npm install

```

### 使用 hexo 

现在 hexo 已经安装好了，不过还需要进行一些配置，可以参考 [hexo 配置教程](http://www.jianshu.com/p/858ecf233db9)



### 更改主题

我现在使用的是 NexT 主题，详细可参考 [Next 主题 wiki](http://theme-next.iissnan.com/five-minutes-setup.html)



### Hexo 命令

```shell
// 新建文档
hexo new "这是一篇新文章"

// 生成静态页面
hexo g

// 预览, 可打开浏览器进行预览
hexo s

// 发布到 github ，需在站点配置文件中配置正确
hexo d
```


