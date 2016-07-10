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

###语法结构
```java
package com.adam.singleton;

public class Singleton{

  private static Singleton uniqueInstance=null;
  private Singleton(){
    
  };
//在同一类中写一个public static的构造方法。
  public static Singleton getInstance(){
    if (uniqueInstance==null) {
      uniqueInstance= new Singleton();
    }
    return uniqueInstance;
  }
}
```
###巧克力工厂实例
```java
package com.adam.singleton;

public class ChocolateFactory{
  private boolean empty;
  private boolean boiled;

  public static ChocolateFactory uniqueInstance=null;
  private ChocolateFactory()
  {
    empty =true;
    boiled=true;
  }

//1.第一次使用巧克力工厂时，用getInstance方法
//由于是第一次使用，将会new出一个巧克力工厂对象。
//当第二次调用时，由于已经构造好了，则返回原来的实例。
  public static ChocolateFactory getInstance()
  {
    if(uniqueInstance==null)
    {
      uniqueInstance=new ChocolateFactory();
    }
    return uniqueInstance;
  }

//2.给巧克力填料
//使用单例模式的好处是可以解决了多个实例造成的冲突问题。
//当再次填料时，程序会知道填料已完成，不会再次重复给一个新的实例填料。
  public void fill()
  {
    if(empty)
    {
      empty=false;
      boiled=false;
    }
  }
}
```




