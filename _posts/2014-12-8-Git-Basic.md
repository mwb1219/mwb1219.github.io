---
layout: post
category: "Git"
title:  "Git基本语法学习笔记"
tags: [Git]
---
##Joda-Time的使用
目的：Joda-Time 使时间和日期值变得易于管理、操作和理解。
###Joda简介
1.*以Joda的方式向某一瞬间加上90天并输出结果*

	Calendar calendar = Calendar.getInstance();
	calendar.set(2000, Calendar.JANUARY, 1, 0, 0, 0);
	SimpleDateFormat sdf =new SimpleDateFormat("E MM/dd/yyyy HH:mm:ss.SSS");
	calendar.add(Calendar.DAY_OF_MONTH, 90);
	System.out.println(sdf.format(calendar.getTime()));
2.Joda与JDK的互操作性

	Calendar calendar = Calendar.getInstance();
	DateTime dateTime = new DateTime(2000, 1, 1, 0, 0, 0, 0);
	System.out.println(dateTime.plusDays(45).plusMonths(1).dayOfWeek().withMaximumValue().toString("E MM/dd/yyyy HH:mm:ss.SSS");
	calendar.setTime(dateTime.toDate());
###Joda关键日期/时间的概念
joda使用的一下概念，它们可以应用到任何日期/时间库

1.*不可变性*

Joda类具有不可变性，即生成的实例无法被修改。（不可变类的一个优点就是它们是线程安全的）。

	注：joda类的方法都会返回一个Joda类的新实例，同时保持原来的实例不变。
2.*瞬间性（Instant）*

表示时间上的某个精确的时刻

3.*局部性*

joda中有时间片段，它是可以移动的，比如6月份可以使每一年的6月份，可以进行移动

4.*年表*

Joda本质以及设计核心就是年表（它得含义由一个同名的抽象类来捕捉）。从根本上讲，年表是一种日历系统 — 一种计算时间的特殊方式 — 并且是一种在其中执行日历算法的框架。受 Joda 支持的年表的例子包括：ISO(默认)、Coptic、Julian、lslamic

Joda-Time1.6支持8种年表，每一种都可以作为特定的日历系统的计算引擎。

5.*时区*

时区是值一个相对于英国格林威治的地理位置，用于计算时间。要了解事件发生的精确时间，还必须知道发生此事件的位置。任何严格的时间计算都必须涉及时区（或相对于 GMT），除非在同一个时区内发生了相对时间计算（即时这样时区也很重要，如果事件对于位于另一个时区的各方存在利益关系的话）。

DateTimeZone 是 Joda 库用于封装位置概念的类。许多日期和时间计算都可以在不涉及时区的情况下完成，但是仍然需要了解 

DateTimeZone 如何影响 Joda 的操作。默认时间，即从运行代码的机器的系统时钟检索到的时间，在大部分情况下被使用

	timezone database :http://www.iana.org/time-zones
	joda-time http://www.joda.org/
