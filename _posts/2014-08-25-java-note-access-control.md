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
2. every package has only one **public** class in that file. ??
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

	