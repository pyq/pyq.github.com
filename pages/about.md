---
layout: page
title: "About"
description: ""
---
{% include JB/setup %}
##code for post
```
$ rake post title="Hello World"

rake page name="about.md"

// or you can do like rake page name="pages/about.md" this make a nested page 
rake page name="pages/about"
//this will create the file: ./pages/about/index.html
```

##code for publish
```
git add .
git commit -m "Add new content"
git push origin master
```