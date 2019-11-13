![1.png](http://ww1.sinaimg.cn/large/9b13c8fdly1g8vb3q4vm3j20c7084408.jpg)

[详细参考](https://www.cnblogs.com/aspirant/p/9002663.html)


- Provider： 暴露服务的服务提供方
- Consumer： 调用远程服务的服务消费方
- Registry： 服务注册与发现的注册中心
- Monitor： 统计服务的调用次数和调用时间的监控中心
- Container： 服务运行容器


# Dubbo 提供的负载均衡策略

- Random LoadBalance(默认，基于权重的随机负载均衡机制)
    - 随机，按权重设置随机概率。
    - 在一个截面上碰撞的概率高，但调用量越大分布越均匀，而且按概率使用权重后也比较均匀，有利于动态调整提供者权重。

- RoundRobin LoadBalance(不推荐，基于权重的轮询负载均衡机制)
    - 轮循，按公约后的权重设置轮循比率。
    - 存在慢的提供者累积请求的问题，比如：第二台机器很慢，但没挂，当请求调到第二台时就卡在那，久而久之，所有请求都卡在调到第二台上。

- LeastActive LoadBalance
    - 最少活跃调用数，相同活跃数的随机，活跃数指调用前后计数差。
    - 使慢的提供者收到更少请求，因为越慢的提供者的调用前后计数差会越大。

- ConsistentHash LoadBalance
    - 一致性 Hash，相同参数的请求总是发到同一提供者。(如果你需要的不是随机负载均衡，是要一类请求都到一个节点，那就走这个一致性hash策略。)
    
[详细参考](https://github.com/Snailclimb/JavaGuide/blob/master/docs/system-design/data-communication/dubbo.md)


    
