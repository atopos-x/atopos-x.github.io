---
title: Java01
aliases: 
tags:
  - Java
date: 2025-01-09
lastmod: 2025-04-17
time: 13:55
---
## 随堂笔记
### String、Stringbuffer、StringBuilder的区别
Stringbuffer是由synchronized修饰的，所以是加锁的，是并发安全的
### ArrayList和LinkedList
LinkList是一个队列，并且底层实现了Deque接口，如果一个类是实现了Deque接口，就表示它是一个双端队列，并且提供了对头部和尾部添加元素的方法。
### CopyOnWritearrayList的底层原理是怎么样的？
1. 首先CopyOnWritearrayList内部也是用数组来实现的，在向CopyOnWritearrayList添加元素时，会复制一个新的数组，写操作在原数组上进行，读操作在原数组上进行
2. 并且，写操作会加锁，防止出现并发写入，导致丢失数据的问题
3. 写操作结束后，会把原数组指向新数组
4. CopyOnWritearrayList允许在写操作时来读取数据，大大提高了读的性能，因此适合读多写少的应用场景，但是CopyOnWritearrayList会比较占内存，同时可能读到的数据不是实时最新的数据，所以不适合实时性要求很高的场景
### ReentrantLock中的tryLock和lock有什么区别？
```java
//阻塞加锁，直到加到锁，方法也没有返回值
reentrantLock.lock(); 
//非阻塞加锁，具有返回值：true加锁成功，false加锁失败
boolean result = reentrantLock.tryLock(); 
```
### 