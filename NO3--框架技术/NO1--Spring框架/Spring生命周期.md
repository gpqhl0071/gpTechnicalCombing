# Spring 中的 bean 生命周期

[图片来源](https://www.xadmin.net/what-is-spring-container-callbacks-or-spring-lifecycle-methods/)
![3.png](http://ww1.sinaimg.cn/large/9b13c8fdly1g8wi8adxosj20im0e0762.jpg)

中文版的图
![4.png](http://ww1.sinaimg.cn/large/9b13c8fdly1g8wil3o3ewj20k308p0vu.jpg)


## 1. initialization 和 destroy

**几种调用方式：**
1. 实现InitializingBean和DisposableBean接口
1. 在bean的配置文件中指定init-method和destroy-method方法
1. 使用@PostConstruct和@PreDestroy注解

## 2. 实现*Aware接口 在Bean中使用Spring框架的一些对象

有些时候我们需要在 Bean 的初始化中使用 Spring 框架自身的一些对象来执行一些操作，比如获取 ServletContext 的一些参数，获取 ApplicaitionContext 中的 BeanDefinition 的名字，获取 Bean 在容器中的名字等等。为了让 Bean 可以获取到框架自身的一些对象，Spring 提供了一组名为*Aware的接口。

- **ApplicationContextAware**: 获得ApplicationContext对象,可以用来获取所有Bean definition的名字。
- **BeanFactoryAware**:获得BeanFactory对象，可以用来检测Bean的作用域。
- **BeanNameAware**:获得Bean在配置文件中定义的名字。
- **ResourceLoaderAware**:获得ResourceLoader对象，可以获得classpath中某个文件。
- **ServletContextAware**:在一个MVC应用中可以获取ServletContext对象，可以读取context中的参数。
- **ServletConfigAware**： 在一个MVC应用中可以获取ServletConfig对象，可以读取config中的参数。

[更多参考](https://github.com/Snailclimb/JavaGuide/blob/master/docs/system-design/framework/spring/SpringBean.md)