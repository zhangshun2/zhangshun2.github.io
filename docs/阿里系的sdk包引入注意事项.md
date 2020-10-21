# 阿里系的sdk包引入注意事项
---
>@author zhangs

## 引入SDK包

* 有一部分实时更新的sdk包要从文档用例提供的最新的sdk包或者别的地方拉下来一个最新的jar
    * 在当前module下创建lib文件夹之后把jar放进去
    * 之后指定在dependency的systemPath中

> systemPath用例如下
~~~xml
<systemPath>${pom.basedir}/lib/XXX.jar</systemPath>
~~~