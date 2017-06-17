---
layout: post
title: "Java 集合框架总览"
description: "类图及总括"
date: 2017-06-17 23:33:00
tags: [java,数据结构]
comments: true
share: true
---

## 框架总览图

* Java集合是java提供的工具包，包含了常用的数据结构：集合、链表、队列、栈、数组、映射等。Java集合工具包位置是java.util.*
* Java集合主要可以划分为4个部分：List列表、Set集合、Map映射、工具类(Iterator迭代器、Enumeration枚举类、Arrays和Collections)

![java collections UML](/images/2017-06-17-java-collection.jpg)

## 总括

> 从类图可以看出可以分为 Collection 和 Map 两个主干。

### Collection

> 接口，集合的抽象，包含了集合的基本操作和属性，并且 Collection 可以分为 List 和 Set 两类。

* List是一个**有序**的队列，每一个元素都有它的索引。第一个元素的索引值是0。List的实现类有LinkedList, ArrayList, Vector, Stack。
* Set是一个**不允许有重复元素**的集合。Set的实现类有HastSet和TreeSet。**HastSet 通过 HashMap 实现，TreeSet 通过 TreeMap 实现。**

### Map

> 对于key -> value 映射的接口，其中每个元素包含一个 key 和 key 对应的 value。

* AbstractMap是个抽象类，它实现了Map接口中的大部分API。

* HashMap，TreeMap，WeakHashMap都是继承于AbstractMap。

* Hashtable虽然继承于Dictionary，但它实现了Map接口。

### Iterator & Enumeration

* Iterator是遍历集合的工具，即我们通常通过Iterator迭代器来遍历集合。我们说Collection依赖于Iterator，是因为Collection的实现类都要实现iterator()函数，返回一个Iterator对象。ListIterator是专门为遍历List而存在的。
* Enumeration，它是JDK 1.0引入的接口。作用和Iterator一样，也是遍历集合；但是Enumeration的功能要比Iterator少。在上面的框图中，Enumeration只能在Hashtable, Vector, Stack中使用。

### Collections & Arrays

> 操作数组、集合的两个工具类。
