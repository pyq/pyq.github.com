---
layout: post
title: "Java compile line"
description: "java compiling from command line"
category: "Java"
tags: [java]
---
{% include JB/setup %}

```
cd xxx/
javac a.java
java a
```

###if a project hava a.java and b.java && a.java use object of b then
```
cd xxx
javac *.java
java a
```

###if a.java and b in package p.q
we should put the class in  the dir p/q/ under current path