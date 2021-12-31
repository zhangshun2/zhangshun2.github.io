# KAFKA

参考:
* [官方文档](http://kafka.apache.org/intro)

## 简介
* 基于``tcp``协议
* 由客户端和服务端组成
* 分布式系统
* 提供了三个关键功能
    * 发布和订阅的消息模型
    * 支持持久化流数据
    * 对流提供事件机制<br>(To process streams of events as they occur or retrospectively)
* 单条流数据组成
    * 键
    * 值
    * 时间戳
    * 元数据 
* 架构<br>
    * kafka的存储层被称为kafka的代理,也可以叫做存储桶
    * kafka的最大单位是主题,提供了订阅和消费功能
    * 主题存在代理中,代理可以是多个
    * 主题下面有分区,相同的键存到相同的分区
    * 先写入的先读取,顺序可以保证
![结构图](../../pic/streams-and-tables-p1_p4.png)       