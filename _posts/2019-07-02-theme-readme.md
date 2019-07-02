---
title: "theme设置"
last_modified_at: 2019-07-02T15:40:02-05:00
excerpt_separator: "<!--more-->" #插入这个以后列表里文章内容就只显示它之前的
excerpt: "minimal mistake主题设置相关信息，什么东西在哪里设置，什么东西放哪里，在哪里找等等。"

categories:
#  - 主题设置
tags:
  - 主题
  - 主题设置
  - readme
---
## minimal mistake主题设置笔记

### _config.yml

大部分设置都在`_config.yml`中：默认作者、sidebar content
各文章网页头可以`_config.yml`中的defaults设置。关于type的解释：The different types that are available to you are pages, posts, drafts or any collection in your site. While type is optional, you must specify a value for path when creating a scope/values pair.

网站导航在`/_data/navigation.yml`
各种网页在`/_pages/`这里面的页面不能显示related
- 首页是`home.md`，布局也在里面设置
- 里面有对全站文章分类显示的框架页面，如按年月日、按collection、按tag、按catalog
collections分类是用文件夹进行的，如`_pets`、`_recipes`

tag和catalog是在post头写的，区别就是tag比较随意，用tag就够了。
`_config.yml`中
```yaml
# Outputting
permalink: /:categories/:title/
``` 
去掉`/:categories`就可以用中文categories了

广告在`/_layout/default.html`_待定。。。_测了一下不显示，adblock倒是有反应，估计要自己账号。

更改后的footer放在`/_inludes/footer.html`去掉feed和“关注”文字，源git有“关注”显示的代码，但是示例网页蜜汁没有，看源代码也没有那句，不知道哪里去掉的。。。

图片等杂物放在`/assets/`
favicon路径在`/_includes/head/custom.html`中设置，现在放在`\assets\images`
header大图宽1280
feature图，单张宽580
插图推荐尺寸150x150，580x300，1200x400，300x200，600x300

作者信息在`/_data/authors.yml`，在post头中与默认作者进行切换。

sidebar可设定为显示作者或者导航，显示作者时下方会一起显示sidebar content。




如果遇到html被显示出来，这是因为marddown到html转换有bug，去掉被显示那句前的空格就好了。

多国语言翻译在`\_data\ui-text.yml`

主题相关的post，tag是“主题”
格式相关的post，tag是“格式”

## 有用外链
提供空白占位图的网站[placeholder.com](https://placeholder.com/)
提供小logo和著名网站logo的网站[Font Awesome](https://fontawesome.com/icons?d=gallery&s=solid&m=free)
做浏览器小图标的网站[favicon generator](https://realfavicongenerator.net/)


commit note
