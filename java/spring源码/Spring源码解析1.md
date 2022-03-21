# 1.Spring的结构组成

 

## xmlBeanfactory

继承自

### DefaultListableBeanFactory

> 该类时对整个Bean加载的核心部分
>
> 是Spring注册以及加载bean的默认实现

#### 相关时序图

<img src="D:\java\git\source\zhangshun2.github.io\java\spring源码\pic\DefaultListbaleBeanFactory.png" style="zoom:150%;" />

### 二者区别

xmlBeanFactory实现了自定义的资源读取器(针对xml

xmlBeanDefinitionReader

#### xmlBeanDefinitionReader时序图



<img src="D:\java\git\source\zhangshun2.github.io\java\spring源码\pic\xmlBeandifinitionReader.png" style="zoom:150%;"  align = 'left'/>





### XMLBeanFactory初始化时序图

#### 完整版

(可跨过

<img src="D:\java\git\source\zhangshun2.github.io\java\spring源码\pic\XmlBeanFactory_new.png" style="zoom:250%;" />



#### 简版

<img src="D:\java\git\source\zhangshun2.github.io\java\spring源码\pic\XmlBeanFactoryTest_main.png" style="zoom:200%;" />

### 配置文件封装

spring的配置文件是通过

#### ClassPathResource

完成的

##### 时序图

<img src="D:\java\git\source\zhangshun2.github.io\java\spring源码\pic\classPathresource.png" style="zoom:200%;" align = 'left'/>



### 加载bean

