---
layout: post
title:  "the-classfile-structure"
---
1.2 The Java Virtual Machine
	- P-Code machine of UCSD Pascal
	- knows nothing of Java programming language , only of a particular binary format, the class file format. 
	 
<br/>
2.1 The class File Format
<br/>

2.2 Data TYPE
	- primittve type 
		- need not be tagged 
	- reference type
	- variables: 
	- argument
	- returned value
	- jvm expect type checking before prior to run time, by compiler
	
	
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
