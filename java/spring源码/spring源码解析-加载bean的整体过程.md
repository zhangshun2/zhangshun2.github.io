# spring源码解析-加载bean的整体过程



总览

首先spring的加载模式是**从xml文件中开始加载**的

了解下加载xml文件的规范,这里有比dom扫描数据更快的方式**SAX**

加载文件的基础就是基于这个

我们加载文件是从**xmlBeanFactory**开始的

这个继承制**DefaultLisableConfigurationFactory**

包含了对于bean的注册与管理,配置读取,注解内容读取等多方面的功能

是beanFactory功能的总览

我们从xmlBeanFactory来看

这里加载方法是先加载父类

这里对于依赖的AB问题做了处理,假设A依赖B,正常情况下,如果B没有被初始化,是需要被初始化的,但是在这里为了防止依赖的循环引用

使用了几个标识接口,识别到这些标识接口就不去加载当前bean的依赖或者成员属性去主动初始化

其次再去**loadBeanDefinition**

这里先去把**xml**解析成为**resource**

再去把resource解析成**document**

这里解析时需要先对文件做验证

一个是文档类型的**DTD**验证,一个是XML格式的**XSD**验证

具体的步骤是

**先去获取对应的验证模式**

再去读**取本地的验证模式**对应的资源,即验证模式文件

验证文件的时候传入的一个参数时**entityResolver**

这个类定义了对于<!doctype内容的具体验证

doctype后面会跟两个字符串,第一个是**publicid** 第二个是**systemid**

这里的entityResolver就是定义了对于这两个字符串的验证规则

之后

当document文档加载结束

就正式进入了解析和注册beanDefinitions的时候了

这时候已经需要**documentReader**来解析doc对象了

首先进入

xmlBeanDefinitionReader的registerBeandefinitions接口 参数时之前准备好的doc和resource对象

之后调用去了BeanDefinitionDocumentReader的registerBeandefinitions方法

而这时的真实调用的类型已经是DefaultBeanDefinitionDocumentReader了

这里是先获取了doc文档的Element的参数

element作为root继续向下传参

这里到最后就是一个解析element标签的过程了

在解析的方法前后还提供了一个pre和probean相关的方法来对于bean的前置和后置做处理



