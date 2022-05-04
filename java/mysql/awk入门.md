# awk入门

## 介绍

> 之于mysql调优

mysql show status之后要去具体的分析参数的时候

需要awk

awk可以用来打印数据

这里比如我们要看查询数,线程数,线程正在使用的数量

就可以mysqladmin -uroot ext | awk '/Queries/{printf("%d" , $4)}'

管理查看mysql配置数据 走管道流传送给下一个命令.awk执行 参数/命令, 打印指定第四列.0的话是全打印

同理写法上可以传参,这样去对脚本做一个参数传递

mysqladmin -uroot ext | awk '/Queries/{a=$4}END{printf("%d" , a)}'

通过上面的方式可以检测到对应的状态变化,并输出到文本中

在没有云服务监控平台或者需要更细粒度的监控数据的话就可以解决问题

