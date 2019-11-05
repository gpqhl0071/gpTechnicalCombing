JDK1.5之后的**java.util.concurrent.atomic**包里，多了一批原子处理类。AtomicBoolean、AtomicInteger、AtomicLong、AtomicReference。主要用于在高并发环境下的高效程序处理,来帮助我们简化同步处理.


**AtomicInteger:**


AtomicInteger，一个提供原子操作的Integer的类。在Java语言中，++i和i++操作并不是线程安全的，在使用的时候，不可避免的会用到synchronized关键字。而AtomicInteger则通过一种线程安全的加减操作接口。

我们先来看看AtomicInteger给我们提供了什么接口:

```
public final int get() //获取当前的值
public final int getAndSet(int newValue)//获取当前的值，并设置新的值
public final int getAndIncrement()//获取当前的值，并自增
public final int getAndDecrement() //获取当前的值，并自减
public final int getAndAdd(int delta) //获取当前的值，并加上预期的值
```

普通线程同步: 

```java

class Test2 {
        private volatile int count = 0;
 
        public synchronized void increment() {
                  count++; //若要线程安全执行执行count++，需要加锁
        }
 
        public int getCount() {
                  return count;
        }
}
```

使用AtomicInteger:

```
class Test2 {
        private AtomicInteger count = new AtomicInteger();
 
        public void increment() {
                  count.incrementAndGet();
        }
   //使用AtomicInteger之后，不需要加锁，也可以实现线程安全。
       public int getCount() {
                return count.get();
        }
}
```

从上面的例子中我们可以看出：使用AtomicInteger是非常的安全的.而且因为AtomicInteger由硬件提供原子操作指令实现的。在非激烈竞争的情况下，开销更小，速度更快。

参考：[https://blog.csdn.net/u013063153/article/details/70332793](https://blog.csdn.net/u013063153/article/details/70332793)


