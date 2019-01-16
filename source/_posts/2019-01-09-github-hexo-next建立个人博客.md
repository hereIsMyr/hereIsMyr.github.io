---
title: github + hexo + next建立个人博客
date: 2019-01-09 09:25:43
tags:
- 工具
categories:
- 工具
---

#### 写在前面
在2019.1.9号这一天，决定建立这个空间用于记录自己web前端学习之旅。终于在某种不可描述的契机下，了解到了github建站，hexo+next定制主题和写作工具（支持markdown写作，扁平化又配色简单的界面深得我心，甚至还适配好了移动端），那么就把捣鼓了一天的个人博客作为第一篇日志，希望我的专业技能和此博客一起不断完善，不断更新~
***
#### 准备工作
- 首先得有个github账号
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
    {% codeblock lang:shell %}
    $ npm install -g hexo-cli
    {% endcodeblock %}
    - 指定blog写作文件夹
    {% codeblock lang:shell %}
    $ hexo init [folder]
    {% endcodeblock %}
    > [<font color="#fc6423">hexo官方文档</font>](https://hexo.io/zh-cn/docs)
2. 下载next主题
    - 在blog写作文件夹根目录下
    {% codeblock lang:shell %}
    $ git clone https://github.com/theme-next/hexo-theme-next themes/next
    {% endcodeblock %}
    > [<font color="#fc6423">next官方文档</font>](http://theme-next.iissnan.com/getting-started.html)
3. 配置写作环境
    - 注意区分此时有两个配置文件，一个位于是位于根目录下的```./_config.yml```，一般称为```站点配置文件```。另一个是位于主题目录下的```./themes/next/_config.yml```，一般称为```主题配置文件```，绝大部分的配置信息在文件里都有很详尽的注释。
    - 启用next主题
    {% codeblock ./_config.yml %}
    # Extensions
    ## Plugins: https://hexo.io/plugins/
    ## Themes: https://hexo.io/themes/
    theme: next
    {% endcodeblock %}
    - 手动创建分类页和标签页
    {% codeblock lang:shell %}
    $ hexo new page "tags"
    $ hexo new page "categories"
    {% endcodeblock %}
4. 写作
5. 部署

