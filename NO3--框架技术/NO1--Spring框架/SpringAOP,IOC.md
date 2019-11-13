# AOP

AOP思想的实现一般都是基于 代理模式
，在JAVA中一般采用JDK动态代理模式，但是我们都知道，JDK动态代理模式只能代理接口而不能代理类。因此，Spring
AOP 会这样子来进行切换，因为Spring AOP 同时支持
[CGLIB、ASPECTJ、JDK动态代理](https://www.cnblogs.com/puyangsky/p/6218925.html)。

- 如果目标对象的实现类实现了接口，Spring AOP 将会采用 JDK 动态代理来生成 AOP 代理类；
- 如果目标对象的实现类没有实现接口，Spring AOP 将会采用 CGLIB 来生成 AOP 代理类——不过这个选择过程对开发者完全透明、开发者也无需关心。

**AOP中的基本概念**：5种类型的通知（Before，After，After-returning，After-throwing，Around）


[AspectJ是一个AOP框架](https://juejin.im/post/5a55af9e518825734d14813f)，它能够对java代码进行AOP编译（一般在编译期进行），让java代码具有AspectJ的AOP功能（当然需要特殊的编译器）


# IOC

IOC是Inversion of Control的缩写，多数书籍翻译成“控制反转”，还有些书籍翻译成为“控制反向”或者“控制倒置”。

[简单来说就是把复杂系统分解成相互合作的对象，这些对象类通过封装以后，内部实现对外部是透明的，从而降低了解决问题的复杂度，而且可以灵活地被重用和扩展。](https://www.cnblogs.com/wang-meng/p/5597490.html)

**IOC的别名：依赖注入(DI)**

**依赖注入(DI)和控制反转(IOC)是从不同的角度的描述的同一件事情**，就是指通过引入IOC容器，利用依赖关系注入的方式，实现对象之间的解耦。

[IOC概念讲解的很形象](https://juejin.im/post/593386ca2f301e00584f8036)

两张图，很直观

![1.png](http://ww1.sinaimg.cn/large/9b13c8fdly1g8wgu8njh3j209905dabq.jpg)

使用IOC后的图，如下。

![2.png](http://ww1.sinaimg.cn/large/9b13c8fdly1g8wguhb6fbj209z04sjsn.jpg)