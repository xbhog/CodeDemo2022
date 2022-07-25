# CodeDemo2022
## 1.并发编程的艺术文章代码
concurrentPro
## 2.工作代码复现
FanXingDemo
## 3.RocketMQ学习--代码实现

1. 集群的搭建
2. 生产者(同步发送，异步以及单向发送消息)，消费者(负载均衡，广播模式)
3. 顺序消息生产

**ROCKETMQ问题：**

学习顺序消息的时候，理想效果应该是：一个订单信息在一个队列中，由一个消费线程进行消费；
但实际效果：多个订单信息在一个队列中，由一个消费线程进行消费。每个订单在不同的队列中，实现采用的订单号与队列数量取模的操作。由于队列数量-默认是4-(比较容易碰撞)，加上两个订单号(15103111139L
,15103117235L)之间取的比较接近，造成取模相同。

注：修改订单号，需要在个位和十位修改，百位及以上修改与4取模结果还是一样的，没有改变。

5. 延时消费