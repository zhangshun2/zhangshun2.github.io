# java反射



## 作用

* 操纵字节码文件
* 操作代码片段

## 应用

* ioc和di
* aop
* 预防反射攻击

## 核心类

* class
* method
* field
* constructor

## 代码操作

##### 获取类字节码文件的三种方式

```
// 获取类字节码文件的三种方式
Class<? extends Apple> appleClassGet1 = apple.getClass();
Class<? extends Apple> appleClassGet2 = Apple.class;
// 注意,如果只是想加载类的静态代码块,可以用Class.forName("完整类名");的形式来触发静态代码块的加载
Class<?> appleClassGet3  = Class.forName("org.example.react.Apple");
System.out.println(appleClassGet1.getName());
System.out.println(appleClassGet2.getName());
System.out.println(appleClassGet3.getName());
```



##### 通过反射获取实例对象

```
// 通过反射获取实例对象
Object appleReact = appleClassGet3.newInstance();
```

##### 通过反射获取所有对应的字段

```
Field[] declaredFields = appleClassGet3.getDeclaredFields();
for (Field field : declaredFields){
    System.out.println(field.getName());
}
```

##### 通过反射获取所有的方法

```
Method[] methods = appleClassGet3.getDeclaredMethods();
for (Method method : methods){
    System.out.println(method.getName());
}
```

##### 给对象赋值

```
// 给对象赋值
// 假设知道String name
Field name = appleClassGet3.getDeclaredField("name");
// 私有字段需要打破封装
name.setAccessible(true);
// 赋值
name.set(appleReact , "测试反射修改属性");
Apple appleNew = (Apple)appleReact;
String nameNew = appleNew.getName();
System.out.println(nameNew);
```

##### 反射调用方法

```
// 反射调用方法
Method getName = appleClassGet3.getDeclaredMethod("getName"/** , 返回值的类型 **/);
Object invoke = getName.invoke(appleReact);
System.out.println(invoke);
```

##### 获取并调用构造方法

```
// 获取构造方法
Constructor<?>[] declaredConstructors = appleClassGet3.getDeclaredConstructors();
for (Constructor constructor : declaredConstructors){
    constructor.setAccessible(true);
    Class[] parameterTypes = constructor.getParameterTypes();
    // 有参数
    if (null != parameterTypes && parameterTypes.length > 0){
        Object instance = constructor.newInstance("ceshi1", 2);
        System.out.println(instance);
        // 无参数
    }else {
        Object instance = constructor.newInstance();
        System.out.println(instance);
    }

}
```

##### 获取一个类的父类以及父类的父类

```
private static void extracted(Class<?> appleClassGet3) {
    Class<?> superclass = appleClassGet3.getSuperclass();
    System.out.println(superclass.getName());
    if (Object.class != superclass){
        extracted(superclass);
    }
}
```

##### 获取一个类的所有接口

```
Class<?>[] interfaces = appleClassGet3.getInterfaces();
for (Class<?> c : interfaces){
    System.out.println(c.getName());
}
```