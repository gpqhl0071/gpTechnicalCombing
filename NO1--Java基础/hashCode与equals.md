# hashCode（）介绍  

hashCode() 的作用是获取哈希码，也称为散列码；它实际上是返回一个int整数。这个哈希码的作用是确定该对象在哈希表中的索引位置。hashCode() 定义在JDK的Object.java中，这就意味着Java中的任何类都包含有hashCode() 函数。

散列表存储的是键值对(key-value)，它的特点是：能根据“键”快速的检索出对应的“值”。这其中就利用到了散列码！（可以快速找到所需要的对象）

参考 :[https://www.jitendrazaa.com/blog/java/what-is-the-need-to-override-hashcode-and-equals-method/](https://www.jitendrazaa.com/blog/java/what-is-the-need-to-override-hashcode-and-equals-method/) 


![1.png](http://ww1.sinaimg.cn/large/9b13c8fdly1g8ltsrf5tuj20hg0860wy.jpg)

`
如上图所示，每个对象都根据其具有的哈希码放置在哈希桶中。
不必每个不同的对象都必须具有不同的哈希码。
哈希码被用来缩小检索结果。
当我们尝试在HashMap中插入任何键时，它首先检查是否存在其他具有相同哈希码的对象，如果是，则它检查equals（）方法。
如果两个对象相同，则HashMap不会添加该键，而是将新值替换旧值。
`