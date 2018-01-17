---
title: redis在高并发请求下会出现问题吗？
date: 
top: 8888 #整数，越大越靠前
tags: [redis,高并发]
categories: [redis]
description:
---
## redis简介
1.key-value形式的nosql存储系统
2.单线程，不会发生线程安全问题
3.性能高，Redis读的速度是110000次/s,写的速度是81000次/s
## redis在极高的并发情况下会出现哪些问题
在java中，一般是使用jedis作为客户端连接redis，虽然redis是单线程的，但是jedis是多线程的，并且jedis每次操作都会对redis发起一次连接。当jedis作为客户端，对redis发起大量的并发请求时，redis会排队处理连接请求，从而导致客户端的连接超时，从而出现各种各样的问题
## 解决方法
1.jedis通过连接池来连接redis，这样可以限制最大连接数，以防止连接数过大时，redis读写速度跟不上
2.在jedis对redis发起set，get等高频率操作时，加上锁，保证同一时刻只有一个线程调用
