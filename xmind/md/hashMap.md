# hashMap

## ArrayList

### as方法得到的是ArrayList的视图

- 无法进行增删改查
- 需要通过ArrayList的构造来创建一个真正的list

## collection

### 迭代

- 方法

	- for
	- for-each
	- stream
	- iterator

## 遍历

### enumeration

- 2个函数式接口
- 不支持增删改查
- 除了Vector和HashTable这些古老集合不推荐使用

### iterator

- 3个函数式接口
- 支持增删改查

## 快速失效

### fast-fail

- 字面意思是快速失败

	- 不如出错了抛出异常

- 集合中的情况

	- 抛出修改并发异常

		- 实际发生情况

			- 预期修改次数和实际修改次数不一致
			- 预期修改次数是通过迭代器的方法修改的
			- 实际修改次数是通过集合自身的方法进行删改的时候修改得到
			- 所以使用了集合自身修改时,迭代器内的预期修改次数没有发生变化,这时候出现了这种问题

### fast-safe

- 避免异常
- 可以使用一下实现了fast-safe的集合类
- 比如copyOnWriteArrayList

	- 写时拷贝副本
	- 对副本加锁
	- 副本修改后将原容器的引用引向新容器
	- 思想: 读写分离

## 删除元素

### 使用迭代器

### 只删除单个的时候可以使用for-each.并且break出当前循环

### 使用fast-safe的集合类

### 使用steam的filter方法生成一个新的过滤过的集合

## list和fast-safe的list

### ArrayList

- 不支持同步

### CopyOnWriteArrayList

- 支持同步
- 写时复制
- 副本加锁
- 处理完删除等操作后,引用地址指向新引用

## 跳表

### ConcurrentSkipListMap

- 支持并发且现成安全
- 以空间换时间来实现链表内的快速查询
- 对比

	- ConcurrentSkipListMap

		- 基于跳表
		- 支持排序

	- ConcurrentHashMap

		- 基于hash桶和红黑树
		- 不支持排序

