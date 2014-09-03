---
layout: post
title: "Java Note Inner Classes"
description: "Inner Classes"
category: "java"
tags: [java]
---
{% include JB/setup %}
#Inner Classes
1. inner class is not composition.  a class definition with another class definition.
2. make an object of the inner class anywhere except from within a non-static method of the outer class, you must specify the type as __OutClassName.InnerClassname__ (that's to say outer class non-static could use directly?)
3. an object of inner classs has a link to the enclosing object that made it, so it can access the members of that enclosing object without anys special qualifications. (even privated members)
4. To get the reference to the outer class object, use __OutClassName.this__. for creating the inner class object, use __OutClassInstance.new Inner()__
5. Local inner class... just valid in the special scope. ?
6. Anonymous inner classes: create an object of an anonymous class that inherited from xx. (the semicolon at the end is like other place ;)
7. **use** an object(thing even primitive type) that defined out side the anonymous inner class, the argument should be final. (if not use no need.)
8. cannot have a named construtor in an anonymous class(since there is no name!) but could instance initialization.
9. Nested Class (make the inner class static). it means 1you don't need an outer-class object in order to create an object of a nested class; 2you can't access a non-static outer-class object from an object of a nested class.
10. A nested class does not have a special this reference, which makes it analogous to a static method.
11. a nested class can be part of an interface.
12. It doesn't matter how deeply an inner class may be nested- it can transparently access all the members of all the classes it is nested within.
13. __Why inner class ?__ 
>each inner class can independently inherit from an implementation. Thus the inner class is not limited by whether the outer class is already inheriting from an implementation. (a solution of __multiple-inheritance__ it allow you to inherit from more than one non-interface)

14. additional features: see in book p261
15. Closures and callbacks, not really understand just give some code here

```
//otherfile
interface Incrementable {
  void increment();
}

// Very simple to just implement the interface:
class Callee1 implements Incrementable {
  private int i = 0;
  public void increment() {
	  i++;
	  System.out.println(i); 
	  }
}
class MyIncrement {
  public void increment() { System.out.println("Other operation"); }
  static void f(MyIncrement mi) { mi.increment(); }
}
// If your class must implement increment() in
// some other way, you must use an inner class:
class Callee2 extends MyIncrement {
  private int i = 0;
  public void increment() {
    super.increment();
    i++;
    System.out.println(i);
  }
  private class Closure implements Incrementable {
    public void increment() {
      // Specify outer-class method, otherwise
      // you’d get an infinite recursion:
      Callee2.this.increment();
} }
  Incrementable getCallbackReference() {
    return new Closure();
  }
}
class Caller {
  private Incrementable callbackReference;
  Caller(Incrementable cbh) { callbackReference = cbh; }
  void go() { callbackReference.increment(); }
}
public class Callbacks {
	 public static void main(String[] args) {
		    Callee1 c1 = new Callee1();
		    Callee2 c2 = new Callee2();
		    c2.increment();
		    MyIncrement.f(c2); // other + 1
		    Caller caller1 = new Caller(c1);
		    Caller caller2 = new Caller(c2.getCallbackReference());
		    //caller2.increment();
		    caller1.go(); // 1
		    caller1.go(); // 2
		    caller2.go(); // other 2  from 2 because f(c2) +1
		    caller2.go(); // other 3
		  }
		} /* Output:
		Other operation
		1
		1
		2
		Other operation
		2
		Other operation
		3
		*///:~
``` 

16. inherit from an inner class should use the syntax: enclosingClassReference.super for the constructor. (also the base inner class should not be protected. not sure)
17. an inner class cannot be overiden like a method.

