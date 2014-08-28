---
layout: post
title: "Java Note Initialization and Cleanup"
description: ""
category: "java"
tags: [java]
---
{% include JB/setup %}
#Initialization and Cleanup
1. Java more safety: if a class has a constructor, java automatically calls that constructor when an object is created.
2. for the constructor, the **new** expression returns a reference to the newly created object, but the constructor itself has no return value.
3. **method overload** - allow the same method name to be used with different argument types. (distinguished by the unique list of argument types, even differences in the ordering of arguments)  
4. overload: why not based on return values, cause we may only call a method and ignore the return value. (like f(), even has two different f() with two return type)
5. **this** keyword can be used only inside a non-static method. (it produces the reference to the object that the method has been called for.)
6. this() only used inside constructor, and can call only one time, the first thing to do, or will get error.
7. you cannot call not-static methods from inside static methods. (reverse ok), but one case possible is passing a reference to an object into the static method(or create its own object.) like main(), then via the reference call non-static methods. 

8. gabage collection and finalization  (1,your object might not get garbage collected 2, garbage collection is not destruction. 3, garbage collection is only about memory) --- many more things need to more reading	
9. an uninitialized local is a programmer error, a field in a class would have default value.
10. **char** value is a zero which prints as a space, for automatically initialize. for object is null

11. static can't apply to local variables, but to fields.
12. static initialization occurs only if it's necessary. and is executed only once: the 1st time you make an object of that class *or the 1st time you access a static member of that class*.(even never make an oject of that class)
13. the order of initialization is static 1st, non-static ojbcts 2nd, then constructor(object created)
14. varargs: type...  it's possible to pass zero argument to a vararg list. should use a variable argument list on one version of an overloaded method, otherwise would be easily ambiguous
15. enums are classed and have their own methods. (ordinal(): indicate the declaration order of a particular enum constant, values(): produces an array of all values of the enum constatns.)
