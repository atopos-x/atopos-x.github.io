---
title: Java试题
aliases: 
tags:
  - Java
date: 2025-01-09
lastmod: 
time: 13:55
---
## 利用反射改变字符串，保证引用不变
```java
String s = new String("abc");  
// 在这中间添加N行代码，但必须保证s引用不变，最终的输出将变为abcd

// 反射  
Field value = s.getClass().getDeclaredField("value");  
value.setAccessible(true);  
value.set(s,"abcd".toCharArray());
  
System.out.println(s);
```
## intern方法的使用
```java
String s1 = new String("abc");  
String s2 = "abc";  
// s1 == s2?  
System.out.println(s1 == s2);  // false  
  
String s3 = s1.intern();  
// s2 == s3?  
System.out.println(s2 == s3); // true
```
String对象中的intern方法，首先会检查字符串常量池中是否存在"abc"，如果存在则返回该字符串的引用，如果不存在，则把"abc"添加到字符串常量池中，并返回该字符串的引用