---
layout: post
title: "jave class problem"
description: ""
category: ""
tags: []
---
{% include JB/setup %}
#some problem on chapter 1.3 
###from Algorithms 4th Edition.pdf
##1.1nested class
for example:

![pic](http://media-cache-ec0.pinimg.com/originals/ea/db/0b/eadb0b5e82599d9365f726d9f63b2e97.jpg)

here **Node and its client code are in the same class in all of our implementations and not accessible by clients of that class, so we still enjoy the benefits of data abstraction.**

##1.2 Iterable collections
jave foreach code

```
for (Transaction t : collection)    {  StdOut.println(t);  }
```
equivalant to

```
Iterator<String> i = collection.iterator();    while (i.hasNext())    {       String s = i.next();       StdOut.println(s);    }
```
therefore we need implement iterator() which is in the class Iterator.


##1.3 generics
###special attention
for creating a generic array, we cannot write like

```
a = new Item[cap];
```
we should do like this

```
a = (Item[]) new Object[cap];
```