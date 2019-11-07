> Java技术体系中所提倡的 自动内存管理
> 最终可以归结为自动化地解决了两个问题：给对象分配内存 以及
> 回收分配给对象的内存，而且这两个问题针对的内存区域就是Java内存模型中的 堆区。

- 垃圾回收机制的意义

- 如何确定一个对象是否可以被回收？

- 垃圾收集算法
    - 标记清除算法
    - 复制算法
    - 标记整理算法
  -   分代收集算法(目前主流的垃圾收集器都会采用分代回收算法)
        1. 新生代（Young Generation）
        1. 老年代（Old Generation）
        1. 永久代（Permanent Generation）

- 垃圾收集器

详细内容参考：[https://blog.csdn.net/justloveyou_/article/details/71216049](https://blog.csdn.net/justloveyou_/article/details/71216049)


更多参考

[https://github.com/Snailclimb/JavaGuide/blob/master/docs/java/jvm/JVM%E5%9E%83%E5%9C%BE%E5%9B%9E%E6%94%B6.md](https://github.com/Snailclimb/JavaGuide/blob/master/docs/java/jvm/JVM%E5%9E%83%E5%9C%BE%E5%9B%9E%E6%94%B6.md)