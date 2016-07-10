# java设计模式之二单例模式(Singleton)

##一些理论

* 有些对象我们只需要一个实例
* 如果有多个实例会造成冲突
* 单例模式：确保一个类只有一个实例，并提供一个全局访问点。
* 

##如何实现

###私有化构造方法
```java
public class Test{
  private Abc(){
  };
  
  //由于构造方法被写成private，则在当前类之外不能用new构造新的实例。
}

```


