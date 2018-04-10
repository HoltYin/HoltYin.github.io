---
title: RabbitMq延时队列
tags: [RabbitMq]
categories: [RabbitMq]
top: 100
---
## 应用场景
   1.订单业务：用户下单之后30分钟内不处理的话，自动放弃该订单
## 消息的TTL
   TTL即Time To Live的缩写，RabbitMQ可以对队列和消息分别设置TTL。设置在队列上，
   即队列没有消费者连接时，消息的保留时间，也可以单独为消息设置TTL。超过了这个时间，
   我们认为这个消息就死了，称之为死信。
   <img src="/images/rabbitmq/1523344240.jpg" >
   
   参数解释：
   
创建queue时参数arguments设置了x-dead-letter-routing-key和x-dead-letter-exchange，会在x-message-ttl时间到期后把消息放到x-dead-letter-routing-key和x-dead-letter-exchange指定的队列中达到延迟队列的目的
## 延迟队列的实现
   rabbitmq实现延迟队列的流程图
   <img src="/images/rabbitmq/1523344918(1).jpg" >
