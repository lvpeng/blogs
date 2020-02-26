---
layout: post
title:  "Java Package 与 Class 关系"
---

### Java Package 与 Class 关系
<br/>
```java
package lee;
public class Hello
{
	public static void main(String[] args)
	{
		System.out.println("Hello,World");
	}
}
```
<br/>
```bash
java -d . Hello.java
```
<br/>
### 当前Hello.java源文件路径下并没有Hello.class ， 而是在该路径新生成了lee目录*
<br/>