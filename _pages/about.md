---
permalink: /about/
author_profile: true
sidebar:
  - title: "Title"
    image: http://placehold.it/350x250
    image_alt: "image"
    text: "Some text here."
  - title: "Another Title"
    text: "More text here."
  - title: "显示navigation.yml里的某一组"  
    nav: docs
---
this is about
我的sidebar上部是作者，下部是Custom sidebar content

# 显示在默认作者下面 Custom sidebar content
```yaml
sidebar:
  - title: "Title"
    image: http://placehold.it/350x250
    image_alt: "image"
    text: "Some text here."
  - title: "Another Title"
    text: "More text here."
  - title: "doc"  
    nav: docs  
```