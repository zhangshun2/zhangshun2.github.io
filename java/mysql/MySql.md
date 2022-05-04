# MySql优化

> 讲述相关优化
>
> > 学习地址 : @link https://www.bilibili.com/video/BV1DC4y1s7XN?p=2&spm_id_from=pageDriver



## 优化思路

![](.\pic\MySQL服务器调优思路.png)

概括:

查看status

判断是否高峰期缓存失效

如果存在不定时卡顿开启慢sql查询找到有问题的sql

profiling和explain分析语句

如果语句执行时间长: 表关联,索引,语句本身 进行优化

如果语句等待时间长:调优服务器参数

都解决的话初步压测判断瓶颈.

实在不行加机器

