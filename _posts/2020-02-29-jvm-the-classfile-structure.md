---
layout: post
title:  "the-classfile-structure"
---

# 1.2 The Java Virtual Machine		
	- P-Code machine of UCSD Pascal
	- knows nothing of Java programming language , only of a particular binary format, the class file format. 
	 
2.1 The class File Format

2.2 Data TYPE
	- primittve type 
		- need not be tagged
		- range? 
		- signed?
		- default value? 
		- two's complement
	- reference type
	- variables: 
	- argument
	- returned value
	- jvm expect type checking before prior to run time, by compiler

2.4 Reference Types and Values
   > There are three kinds of reference types: class types, array types, and interface types. 
		1 what is type?  -> variables ?  
		2 Person p , Person is Class Type 
		3 ```
			public interface Relatable {
        
    // this (object calling isLargerThan)
    // and other must be instances of 
    // the same class returns 1, 0, -1 
    // if this is greater than, 
    // equal to, or less than other
    public int isLargerThan(Relatable other);
}
		  ```
      4 modifier keyword 
	  5 Stack , Heap , Method area
	  6 Access Modifier: public , protected , default , private
	  7 static, final, abstract 
		- static : 
		- abstract : 
		- 
		 ||       | public | protected | default  | private |  final | abstract |  static  |  volatile |  synchronized |
	  8  || class |  √     |    -   	  |  √       |  -	   |	√ 	|   √      |    -     |
		 || member | √     |    √	  |  -       |   ✔	   |    √   |   -      |    √	  |
		 || method | √     |   		  |          |  	   |
		 || interface | √  |   		  |        	 |  	   |		| 		   |
		 
		 
		 final :　subclass can not inherits from parent class , and can not modify field with final modifier
		 abstract: 
		 private : subclass can access parent class 's private member
		 static:
		 
	9　　how compiler control modifier 's access permission?
   Their values are references to dynamically created class instances, arrays, or
class instances or arrays that implement interfaces, respectively.

An array type consists of a component type with a single dimension (whose length
is not given by the type). The component type of an array type may itself be an array
type. If, starting from any array type, one considers its component type, and then
(if that is also an array type) the component type of that type, and so on, eventually
one must reach a component type that is not an array type; this is called the element
type of the array type. The element type of an array type is necessarily either a
primitive type, or a class type, or an interface type.
A reference value may also be the special null reference, a reference to no object,
which will be denoted here by null. The null reference initially has no run-time
type, but may be cast to any type. The default value of a reference type is null.
This specification does not mandate a concrete value encoding null.
	
# The Java® Virtual Machine Specification 4.1 The ClassFile Structure

## A class file consists of a single ClassFile structure:
```
	ClassFile {
	 u4 magic;
	 u2 minor_version;
	 u2 major_version;
	 u2 constant_pool_count;
	 cp_info constant_pool[constant_pool_count-1];
	 u2 access_flags;
	 u2 this_class;
	 u2 super_class;
	 u2 interfaces_count;
	 u2 interfaces[interfaces_count];
	 u2 fields_count;
	 field_info fields[fields_count];
	 u2 methods_count;
	 method_info methods[methods_count];
	 u2 attributes_count;
	 attribute_info attributes[attributes_count];
 ```

## constant_pool_count
	- constant_pool table 
		- Java Virtual Machine instructions 
			do not rely on run-time layout of classes		
		- constant_pool entries format:
		
			cp_info {
			   ul tag; (1 bit indicating the kind of constant. 
					there are 17 kinds of constant)
			   u2 info[];
			}
			
	- valid index range
	- exception: long and double

<br/>	
