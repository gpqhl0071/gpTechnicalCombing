MVC 是一种设计模式,Spring MVC 是一款很优秀的 MVC 框架。Spring MVC 可以帮助我们进行更简洁的Web层的开发，并且它天生与 Spring 框架集成。Spring MVC 下我们一般把后端项目分为 Service层（处理业务）、Dao层（数据库操作）、Entity层（实体类）、Controller层(控制层，返回数据给前台页面)。

# 流程

1. 客户端（浏览器）发送请求，直接请求到 DispatcherServlet。
1. DispatcherServlet 根据请求信息调用 HandlerMapping，解析请求对应的 Handler。
1. 解析到对应的 Handler（也就是我们平常说的 Controller 控制器）后，开始由 HandlerAdapter 适配器处理。
1. HandlerAdapter 会根据 Handler 来调用真正的处理器开处理请求，并处理相应的业务逻辑。
1. 处理器处理完业务后，会返回一个 ModelAndView 对象，Model 是返回的数据对象，View 是个逻辑上的 View。
1. ViewResolver 会根据逻辑 View 查找实际的 View。
1. DispaterServlet 把返回的 Model 传给 View（视图渲染）。
1. 把 View 返回给请求者（浏览器）

[更多参考](https://github.com/Snailclimb/JavaGuide/blob/master/docs/system-design/framework/spring/SpringInterviewQuestions.md)

[How Spring MVC Framework works? How HTTP Request is processed?](https://javarevisited.blogspot.com/2017/06/how-spring-mvc-framework-works-web-flow.html)

