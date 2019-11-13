
[事务基础](../../NO6--数据库/NO1--Mysql/事务.md)

# Spring事务管理接口

- **PlatformTransactionManager**： （平台）事务管理器
- **TransactionDefinition**： 事务定义信息(事务隔离级别、传播行为、超时、只读、回滚规则)
- **TransactionStatus**： 事务运行状态

**所谓事务管理，其实就是“按照给定的事务规则来执行提交或者回滚操作”。** 

[更多参考](https://juejin.im/post/5b00c52ef265da0b95276091)

# Spring编程式和声明式事务

- **编程式事务管理**： 通过Transaction Template手动管理事务，实际应用中很少使用，
- **使用XML配置声明式事务**： 推荐使用（代码侵入性最小），实际是通过AOP实现

[更多参考](https://juejin.im/post/5b010f27518825426539ba38)

