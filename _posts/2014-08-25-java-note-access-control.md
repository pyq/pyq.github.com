---
layout: post
title: "Java Note Access Control"
description: "Access Control"
category: "java"
tags: [java]
---
{% include JB/setup %}
#Access Control
1. package statement should appear as the first **non-comment** in the file (use all lowercase letter)
2. every .java file has only one **public** class in that file.

```
class A{}
public class Solution{
}
```

3. CLASSPATH =.;others;   the '.' is important(current path ??).   For the jar file, should also includes the file name and extention.
4. If two or more packages has same methods cause a collision, we should add the class name explicitly.
5. Java access specifiers  
	public:  
	protected: protected also gives package access. (other classes in the same package may access protected elements)  
	default(package access):  
	private: any method you're certain is only a "helper" method for that class can be made private.
	
6. code style: like above order : public -> protected -> package access -> private.
7. class access: 1there can be one public class per complilation unit(file).  2the name of the *public* class must exactly match the name of the file containing the compilation unit, including capitalization. 3it's possible to have a compilation with no public calss at all.(the name of file is no need to same)
8. class access have 2 choice: package access or **public**. (no private or protected). but the inner class can be private or protected. special case.
9. All the files within the same directory that don't have explicit package declarations are implicitly part of the default package for that directory.
10. if a static member of a class is public. we can access that static member without creating object.

access control ensures that no client programmer becomes dependent on any part of the underlying implementation of a class , and keep user's hands off portions that they shouldn't touch. (implementation hiding).

---

>Variables, methods and constructors which are declared protected in a superclass can be accessed only by the subclasses in other package or any class within the package of the protected members' class.

---
>However if the public class we are trying to access is in a different package, then the public class still need to be imported.

---
####code display
##A.java
```
package package1;

public class A {
	//foo1 public
	public void foo1(){
		System.out.println("foo1: public");
	}
	protected void foo2(){
		System.out.println("foo2: protected");
	}
	void foo3(){
		System.out.println("foo3: package access");
	}
	private void foo4(){
		System.out.println("foo4: private");
	}
}
//same with inherited from class A without public
class AA extends A {
	void testInher(){
		foo1();
		foo2();
		foo3();
		//foo4();  private can't inherit
	}
}
```

##A1.java
```
package package1;

class A1 {
	//foo1 public
	//foo2 protected
	//foo3 package access
	//foo4 private
	public void foo1(){
		System.out.println("foo1: public");
	}
	protected void foo2(){
		System.out.println("foo2: protected");
	}
	void foo3(){
		System.out.println("foo3: package access");
	}
	private void foo4(){
		System.out.println("foo4: private");
	}
}
// cause in the same package, so A11 can access public, protected (inherit) , package access
class A11 extends A1{
	void testMethod(){
		foo1();
		foo2();
		foo3();
		//foo4(); private 
		
	}
}
// here we can also access foo3, means protected method could be accessed by the same package. even not subclass
class A111{
	void testMethod(){
		A1 a = new A1();
		a.foo1();
		a.foo2();
		a.foo3();
		//foo4(); private 
		
	}
}
```

#B.java
```
package package2;
//import package1.A1;
//The type package1.A1 is not visible
//if class is not public, can not use with other class from different package.

import package1.A;
class B {
	void testA(){
		A a = new A();
		a.foo1();
		//a.foo2(); protected not visible!!
	}
}


```

#BA.java
```
package package2;

import package1.A;
//see should import first, or can't find A
public class BA extends A {
	void testMethodinA(){
		foo1();
		foo2();
		//foo3(); package access is not visible in package2
		//foo4();
	}
}

```


>###conlusion:
1. in the same package, class is public or package access would be like the same. all other class in that package can access the public, protected, and default method. (but without inheritation should creat oject first)  like above says, protect gives package access right!!
2. in the different package, non-public class cannot import. we can only use public and protect method(should inherite, B.java has shown) from public class in other package.