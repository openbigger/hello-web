---
# 首页头
layout: splash #这个比home好看，有块块
permalink: /
header:
  overlay_color: "#5e616c"
  overlay_filter: "0.5"
  overlay_image: http://placehold.it/1280x720.jpg #/assets/images/home/header-1280x720.jpg
  actions: #按钮
    - label: "<i class='fas fa-download'></i> 按下去会怎样"
      url: ""
  caption: "Photo credit: [**图片来自这里**](https://#)"    
excerpt: > #可以写html
  这里又可以对网站进行描述描述巴拉巴拉巴拉巴拉的摘要<br />
  <small><a>网站被转发的时候会写这段</a></small>
intro: 
  - excerpt: '头部大图下面的文字。写一些什么呢?就是网站详细信息吧？ Centered with `type="center"`'
# 下面这些块块在手机上看都是竖着摆的，网页上一排三个
feature_row1: # 首页头图下方三个小块
  - image_path: http://placehold.it/480x240.jpg #/assets/images/home/Ko-Chang-500x300.jpg
    image_caption: "Image courtesy of [图片来自这里](https://#)"
    alt: ""
    title: "模块一"
    excerpt: "Everything from the menus, sidebars, comments, and more can be configured or set with YAML Front Matter."
    url: "/west/"
    btn_class: "btn--primary"
    btn_label: "Learn more"
  - image_path: http://placehold.it/400x240.jpg #/assets/images/home/whitebear-500x300.jpeg
    alt: "fully responsive"
    title: "图片大小根据比例调整"
    excerpt: "Built with HTML5 + CSS3. All layouts are fully responsive with helpers to augment your content."
    url: ""
    btn_class: "btn--primary"
    btn_label: "Learn more"
  - image_path: http://placehold.it/400x300.jpg #/assets/images/home/Ko-Chang-500x300.jpg
    alt: "模块三"
    title: "100% free"
    excerpt: "Free to use however you want under the MIT License. Clone it, fork it, customize it... whatever!"
    url: ""
    btn_class: "btn--primary"
    btn_label: "Learn more"       
#三小块下面单独放的
feature_row2: 
  - image_path: http://placehold.it/580x300.jpg #/assets/images/home/Ko-Chang-500x300.jpg
    alt: "customizable"
    title: "图在左边"
    excerpt: "Everything from the menus, sidebars, comments, and more can be configured or set with YAML Front Matter."
    url: ""
    btn_class: "btn--primary"
    btn_label: "Learn more"
feature_row3:
  - image_path: http://placehold.it/580x300.jpg #/assets/images/home/whitebear-500x300.jpeg
    alt: "fully responsive"
    title: "图在上边"
    excerpt: "Built with HTML5 + CSS3. All layouts are fully responsive with helpers to augment your content."
    url: ""
    btn_class: "btn--primary"
    btn_label: "Learn more"
feature_row4:    
  - image_path: http://placehold.it/580x300.jpg #/assets/images/home/Ko-Chang-500x300.jpg
    alt: "100% free"
    title: "图在右边"
    excerpt: "Free to use however you want under the MIT License. Clone it, fork it, customize it... whatever!"
    url: ""
    btn_class: "btn--primary"
    btn_label: "Learn more"    
---
{% include feature_row id="intro" type="center" %}
{% include feature_row id="feature_row1" %}
{% include feature_row id="feature_row2" type="left"%}
{% include feature_row id="feature_row3" type="center" %}
{% include feature_row id="feature_row4" type="right" %}
