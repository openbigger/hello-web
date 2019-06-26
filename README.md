## 建立一个github page的基本步骤
- ## [开始前需要知道的](#开始前需要知道的)
    - [GitHub page可以和不可以](#GitHub-page可以和不可以)
    - [选择哪种主题](#选择哪种主题)

- ## [Learning lab练手](#Learning-lab)
- ## [建站初操作](#建站初操作)
    1. [把一个repo变成Github Pages](#把一个repo变成Github-Pages)
    2. [在本地搭建预览环境](#在本地搭建预览环境)
    1. [选择主题及其设置](#选择主题及其设置)
    1. [添加博客内容](#添加博客内容)
    

> 目录写法
- ```[目录里面的字](#要跳转到的字)```
- ```[Big Title](#big-title)```
>##### 前后的字可以不一样，要跳转到的字的空格用“-”相连。要跳转到的地方必须是个标题，即前面要有#。

> Markdown里写```Markdown或者代码块用键盘1旁边的三个点点引起来```就是代码块，字就不带Markdown格式。前三个点点点后加上代码所用语言会有相应字体和颜色。注意点点点的tab位置。写一小句用`单个点`，字就有背景。
 
# 开始前需要知道的
## GitHub page可以和不可以
[What is GitHub Pages?](https://help.github.com/en/articles/what-is-github-pages)
### 可以
- 三种页面user、organization、project，即三种github.io域名
- 自己买域名来挂
- 免费
- 静态页面
- 插件
- 本机测试 
- 支持Markdown、html
### 不可以
- 不支持 PHP, Ruby, or Python（然而可以用这些来写）
- repo不能私有
- 不能超过1GB，访问量也有限制
## 选择哪种主题
主题可有很多选择如：Jekyll、hexo。先看看网上那些主题，有没有自己想要的。官方推的是Jekyll。

# Learning lab练手
加入[GitHub Pages](https://lab.github.com/githubtraining/github-pages)这个course，可以学习建立GitHub Pages的最基本的东西。
>In this course, you’ll learn how to:
>- Enable GitHub Pages
>- Choose a theme with Jekyll
>- Use YAML front matter
>- Customize your site
>- Create and edit blog posts

- 学习如何把一个repo变成网页
- 学习制作page的git flow，顺便学习保护master
- 接触一下congfig、yaml、posts命名

仅此而已，最后出来的页面不会显示post，因为在线选择theme给出来那些都不显示posts，需要自己进行修改。课程使用的[minimal主题issues](](https://github.com/pages-themes/minimal/issues/14))里有提到。

> 第一次用learning lab时可依照提示fork training-kit，否则装的课程会影响所有repo。不装也没关系，个人喜好。

> 每次进入课程安装的时候，第一次总会失败。删掉课程repo重新来一次就好了。

# 建站初操作
 
### 1. 把一个repo变成Github Pages
[官方入口](https://pages.github.com/)
只需要在setting-GitHub Pages-Source选择以下这几种之一即可
- master branch
- gh-pages branch
- master里的/docs文件夹
>区别
> 1.  项目project页面三种都能选。默认网址为`http(s)://<username>.github.io/<projectname>`或`http(s)://<orgname>.github.io/<projectname>`
> 2. 用户user、orgnization页面只能选择master。默认网址为`<username>.github.io`和`<orgname>.github.io`。这时候的repo名字要是`username`或者`orgname`，也就是一个用户只能有一个这样的页面。
> 3. 选/docs可以自定义域名

打开page网址时，GitHub会根据下面的顺序来寻找首页：
#### index.html-->index.md-->readme.md

所以有了readme就能点开网址看。

### 2. 在本地搭建预览环境
**上面那步做到选择source就够了。**
所有在GitHub里的更改需要commit了才能看，会令branch乱糟糟的，不适合在线编辑。把预览网站的工作拿到本地来就方便多了。
以下翻译整理自
[Setting up your GitHub Pages site locally with Jekyll](https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll)

1. 以windows为例，要先装[Git Bash](https://gitforwindows.org/)（有git的人都有这个），接下来的安装和本地预览环境都要用。
1. 装Ruby。有了它就能装Bundle，装了Bundle才能运行Jekyll，运行了Jekyll就可以本地预览网站。
    1. 在Git Bash中检查是否有Ruby 2.1.0或更高级
        ```bash
        $ ruby --version
        > ruby 2.X.X
        ```

    1. 如果没有Ruby就要去下一个[Ruby+Devkit](https://rubyinstaller.org/downloads/)（网站推荐的那个）。
    
1. 装Bundle
    ```ruby
    $ gem install bundler
    # Installs the Bundler gem
    ```
1. 把库clone下来，记得建个分支。在根目录添加`Gemfile`（不带后缀名），里面写

    ```ruby
    source 'https://rubygems.org'
    gem 'github-pages', group: :jekyll_plugins
    ```
1. 装Jekyll。Git Bash里cd到本地库根目录，运行
    ```bash
    $ bundle install
    > Fetching gem metadata from https://rubygems.org/............
    > Fetching version metadata from https://rubygems.org/...
    > Fetching dependency metadata from https://rubygems.org/..
    > Resolving dependencies...
    ```    
    就把刚才Gemfile的东西装好了。
1. 运行网页预览环境
    ```bash
    $ bundle exec jekyll serve
    > Configuration file: /Users/octocat/my-site/_config.yml
    >            Source: /Users/octocat/my-site
    >       Destination: /Users/octocat/my-site/_site
    > Incremental build: disabled. Enable with --incremental
    >      Generating...
    >                    done in 0.309 seconds.
    > Auto-regeneration: enabled for '/Users/octocat/my-site'
    > Configuration file: /Users/octocat/my-site/_config.yml
    >    Server address: http://127.0.0.1:4000/
    >  Server running... press ctrl-c to stop.

    ```
    不要关哦，浏览器打开`http://localhost:4000`查看本地网站。
### 3. 选择主题及其设置
在网上找好喜欢的主题（那种很多设置，文档详细的为佳），先去本地文件夹查看是否已经存在。不存在的话需要安装或者fork或者用remote theme，存在的话就简单了。主题目录在Ruby的gems目录里，例如：`C:\Ruby25-x64\lib\ruby\gems\2.5.0\gems`

安装需要在`Gemfile`里加上

```ruby
gem "themename"
```
**运行`bunlde`安装主题。**
如果以后不想更新`bundle update`这个主题，就把刚才那句去掉。

**然后`_config.yml`激活主题。**
在网站根目录新建`_config.yml`文件，写

```yaml
theme: themename
```

一个网站可以安装多个主题，但只能激活一个。
在index的最开头加上YAML语句
```yaml
---
layout: home #或者别的主题规定的layout
---
```
运行`bundle exec jekyll serve`查看变化。（每次`_config.yml`更改了以后都要重新运行一次）

### 4. 添加博客内容
博客内容post都装在`_posts`文件夹内。每个post的明明有独特的规则，这样网页才能把它们进行排序、分类和归档。
名字格式为`yyyy-mm-dd-my-title`后缀为md或markdown。以下为合法名字。年月日要过去的并注意时区（可在`_config.yml`中设置）。
```
2016-07-20-writing-jekyll-posts.md
2015-01-03-static-site-generators.markdown
```
根据主题要求，post的开头可能会加上layout、title、tag等信息。如有默认设置，需要在`_config.yml`中写明。
运行一下看看，如果能显示post的主题没有显示post就有可能设置不对，搞搞就好了。
目前为止最小网站的结构如下：
```
├── Gemfile
├── Gemfile.lock
├── _config.yml
├── _posts
│   └──2016-12-04-welcome-to-jekyll.markdown
├── about.markdown
└── index.markdown
```
有个`_site`文件夹是运行环境的时候生成的，不用commit。今后可能还会用到`_layout`、`_includes`、`assets`、`_sass`。
###### 主题的其它设置和内容添加详见主题readme和它的网站。