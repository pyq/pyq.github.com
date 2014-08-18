---
layout: post
title: "Java Note Everything is an Object"
description: ""
category: "Java"
tags: [java, object]
---
{% include JB/setup %}
#Everything is an object Note
1. object reference is on the stack, the pointed object is on heap 
2. primitive types are placed on the stack (more efficient)  
| Primitive type | Size | Minimum | Maximum | Wrapper type|  
|----------------|------|---------|---------|-------------|  | boolean        | —    | —       | —       | Boolean     |    |char            |16 bits|Unicode 0|Unicode 216- 1|Character|  |byte|8 bits|-128|+127|Byte|  |short|16 bits|-215|+215-1|Short|  |int|32 bits|-231|+231-1|Integer|  |long|64 bits|-263|+263-1|Long|  |float|32 bits|IEEE754|IEEE754|Float|  |double|64 bits|IEEE754|IEEE754|Double|  |void|—|—|—￼|Void|  
3. All numeric types are signed, Java array is safety (it is guaranteed to be initialized)
4. the C and C++ ability to “hide” a variable in a larger scope is not allowed,
5. fields(data members) and methods (member functions)
6. default value : char  is null ('\u0000') others are 0 or (0.0 something based on type )
7. local variable don't guarantee default value.(only for the fields of a class)
8. method include several parts: the name, the arguments, the return type and the body. (the method name and argument type are also called *signature*)
9. when hading objects around, you are actually passing references.
10. java don't have "forword referencing problem" (we can call a method, which might be define at the later of file)
11. staic it means that particular field or method is not tied to any particular object instance of that class. 
12. comment documentation
```
//: object/Documentation1.java/** A class comment */public class Documentation1 {  /** A field comment */  public int i;  /** A method comment */  public void f() {}} ///:~```

#exercise solution
```
public class EverythingIsAnObject {
	private int i;
	private char c;
	
	public void printDefaultValue() {
			System.out.println("field int i default value is " + i+"!");
			System.out.println("field char c default value is" + c +"!");
			System.out.println(c == '\u0000');
	}
	
	
	public static void main (String[] args) {
		EverythingIsAnObject ob = new EverythingIsAnObject();
		//excersise 1
		//output should be: 0, null'\u0000'
		ob.printDefaultValue();
		//excersise 2: trivial hello world javac xxx.java java xxx
		//local i can't use cause not initialized(dislike c++ local i override field i)
		//int i;
		//System.out.println("local i" + i);
		
	}

}

class StaticTest {
           static int i = 47;
}
public class Incrementable {
	static void increment() {
		StaticTest.i++;
	}
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Incrementable sf = new Incrementable();
		sf.increment();
		Incrementable.increment();
		increment(); // cause in the Incrementable class already in that class when execute main()
		//You can call increment( ) by itself, because a static method (main( ), in this case) can call another static method without qualification.
		
		System.out.println(StaticTest.i);
		
		System.getProperties().list(System.out);
	    System.out.println(System.getProperty("user.name"));
	    System.out.println(
	    System.getProperty("java.library.path"));
	}

}


```