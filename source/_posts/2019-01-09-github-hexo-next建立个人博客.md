---
title: github + hexo + next建立个人博客
date: 2019-01-09 09:25:43
tags:
- Hexo
- Blog
categories:
- 工具
---

#### 写在前面
在2019.1.9号这一天，决定建立这个空间用于记录自己web前端学习之旅。终于在某种不可描述的契机下，了解到了github建站，hexo+next定制主题和写作工具（支持markdown写作，扁平化又配色简单的界面深得我心，甚至还适配好了移动端），那么就把捣鼓了一天的个人博客作为第一篇日志，希望我的专业技能和此博客一起不断完善，不断更新~
***
#### 准备工作
- 首先得有个github账号，关联ssh
- 安装nodeJS，git
- 建立项目生成GitHub Pages
{% asset_img 20190109112318.png 建立项目生成GitHub Pages %}
{% asset_img 20190109114445.png 打开项目setting查看 %}
{% blockquote %}
打开项目的setting，找到 **GitHub Pages**，你会惊奇的发现github已经帮你把个人站点生成了，可以直接通过url访问~
{% endblockquote %}
***
#### 正式开始
1. 安装hexo
    - 全局安装hexo
    ``` shell
    $ npm install -g hexo-cli
    ```
    - 指定blog写作文件夹
    ``` shell
    $ hexo init [folder]
    ```
    > [<font color="#fc6423">hexo官方文档</font>](https://hexo.io/zh-cn/docs)
2. 下载next主题
    - 在blog写作文件夹根目录下
    ``` shell
    $ git clone https://github.com/theme-next/hexo-theme-next themes/next
    ```
    > [<font color="#fc6423">next官方文档</font>](http://theme-next.iissnan.com/getting-started.html)
3. 配置项
    - 注意区分此时有两个配置文件，一个位于是位于根目录下的``./_config.yml``，一般称为``站点配置文件``。另一个是位于主题目录下的``./themes/next/_config.yml``，一般称为``主题配置文件``，所有的配置信息在文件里都有很详尽的注释说明作用。
4. 写作
    - 新建一篇文章
    ``` shell
    $ hexo new <title>
    ```
5. 部署
    - 开启本地服务预览，需要安装包``hexo-server``
    ``` shell
    $ npm install hexo-server --save
    ```
    在静态模式下，服务器只处理``public``文件夹内的文件，而不会处理文件变动，在执行时，应该先进行编译
    ``` shell
    $ hexo generate
    $ hexo g
    ```
    然后开启服务,就可以预览编辑好的blog
    ``` shell
    $ hexo server
    ```
    - 部署到github
    首先需要安装包``hexo-deployer-git``
    ``` shell
    $ npm install hexo-deployer-git --save
    ```
    然后在``站点配置文件``下找到
    ```
    # Deployment
    ## Docs: https://hexo.io/docs/deployment.html
    deploy:
      type: git
      repo: git@github.com:hereIsMyr/hereIsMyr.github.io.git
      branch: master
    ```
    在这里关联github项目地址，需要注意的是，**GitHub Pages**仅支持``master``分支自动部署站点，所以配置``branch``只能填写``master``
    > 如果需要用github管理写作环境，可以在项目下新建write分支，把写作环境的代码push上去

    部署代码之前先清除已经生成的站点文件
    ``` shell
    $ hexo clean
    ```
    然后可以直接用命令部署
    ``` shell
    $ hexo deploy
    $ hexo d
    ```

