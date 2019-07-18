---
title: "theme设置"
last_modified_at: 2019-07-18T15:40:02-05:00
excerpt_separator: "<!--more-->" #插入这个以后列表里文章内容就只显示它之前的
excerpt: "minimal mistake主题设置相关信息，什么东西在哪里设置，什么东西放哪里，在哪里找等等。"

categories:
#  - 主题设置
tags:
  - 主题
  - 主题设置
  - readme
---
# minimal mistake主题设置笔记
## _config.yml
- 大部分设置都在`_config.yml`中：默认作者、sidebar content
- 各文章网页头可以`_config.yml`中的defaults设置。

## 文件夹
- 网站导航在`/_data/navigation.yml`
- 多国语言翻译在`/_data/ui-text.yml`
- 各种网页在`/_pages/`
  - about/404/contact等
  - 首页是`home.md`，feature row布局在Front matter设置
  - 里面有对全站文章分类显示的框架页面，特别是main导航的网页。如按年月日、按collection、按tag、按catalog
- collections分类是用文件夹进行的，如`_pets`、`_recipes`。

## tag/category
是在post头写的，区别就是tag比较随意，具体怎么分看情况，用tag就够了。
- 主题相关的post，tag是“主题”
- 格式相关的post，tag是“格式”

## 广告
在`/_layout/default.html`_待定。。。_测了一下不显示，adblock倒是有反应，估计要自己账号。

## footer
更改后的footer放在`/_inludes/footer.html`去掉feed和“关注”文字，源git有“关注”显示的代码，但是示例网页蜜汁没有，看源代码也没有那句，不知道哪里去掉的。。。

## 图片
- 图片等杂物放在`/assets/`
- favicon路径在`/_includes/head/custom.html`中设置，现在放在`/assets/images`
- header大图宽1280
- feature图，单张宽580，不同比例不同排法，图片显示尺寸不同。
- 插图推荐尺寸150x150，580x300，1200x400，300x200，600x300

## 作者信息
在`/_data/authors.yml`，在post头中与默认作者进行切换。

## sidebar
可设定为显示作者或者导航，显示作者时下方会一起显示sidebar content。

## gitignory
```yaml
*.gem
*.sublime-project
*.sublime-workspace
.bundle
.DS_Store
.jekyll-metadata
.sass-cache
_asset_bundler_cache
_site
codekit-config.json
example/_site
Gemfile.lock
node_modules
npm-debug.log*
```

## 有用外链
- 提供空白占位图的网站[placeholder.com](https://placeholder.com/)
- 提供小logo和著名网站logo的网站[Font Awesome](https://fontawesome.com/icons?d=gallery&s=solid&m=free)
- 做浏览器小图标的网站[favicon generator](https://realfavicongenerator.net/)
- 免费图片网站[Unsplash](https://unsplash.com/)

## 问题解决
- 代码块后加回车。如果还不能正常显示，前面也加上。
- 主题井号前加回车
- 如果遇到html被显示出来，这是因为markdown到html转换有bug，去掉被显示那句前的空格就好了。
- 文章可全用markdown写，但不能用emoji，否则左上角网站头标题会不见。因为emoji格式带冒号。
- 中文categories解决方法：`_config.yml`中
```yaml
# Outputting
permalink: /:categories/:title/
``` 

去掉`/:categories`就可以用中文categories了

>关于default中type的解释：The different types that are available to you are pages, posts, drafts or any collection in your site. While type is optional, you must specify a value for path when creating a scope/values pair. type可以是pages/posts/drafts和collection名字，默认放置的文件夹就是_pages/_posts/_drafts/:collection，如果文件夹有变则必须把scope加上。不同type在网站中显示的格式不同。如pages就不能显示related。
{: .small}

## 和markdown不一样的格式
更详细的见[2019-07-01-markup](/markup/)
- `{: .notice}`可以把一段话变成有背景的小字，四种颜色
下面的代码块要一句一句包起来。
```yaml
`{: .notice}`
`{: .notice -- danger}`
`{: .notice -- warning}`
`{: .notice -- info}`
```

- 插图格式

```html
<figure>
  <img src="{{ 'https://mmistakes.github.io/minimal-mistakes/assets/images/mm-home-post-pagination-example.jpg' | relative_url }}" alt="archive layout example">
  <figcaption>List view example.</figcaption>
</figure>
```

这样图片会居中，外部补灰色，下方带一行小字。上面的显示结果如下：
<figure>
  <img src="{{ 'https://mmistakes.github.io/minimal-mistakes/assets/images/mm-home-post-pagination-example.jpg' | relative_url }}" alt="archive layout example">
  <figcaption>List view example.</figcaption>
</figure>
