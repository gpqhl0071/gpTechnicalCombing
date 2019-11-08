# 1. BIO (Blocking I/O)

同步阻塞I/O模式，数据的读取写入必须阻塞在一个线程内等待其完成。

**传统 BIO** : BIO通信（一请求一应答）

**伪异步 IO** :
为了解决同步阻塞I/O面临的一个链路需要一个线程处理的问题，后来有人对它的线程模型进行了优化一一一后端通过一个线程池来处理多个客户端的请求接入

# 2. NIO (New I/O)

NIO是一种同步非阻塞的I/O模型，在Java 1.4 中引入了NIO框架，对应 java.nio 包，提供了 Channel , Selector，Buffer等抽象。

NIO提供了与传统BIO模型中的 `Socket` 和 `ServerSocket` 相对应的 `SocketChannel` 和 `ServerSocketChannel` 两种不同的套接字通道实现,两种通道都支持阻塞和非阻塞两种模式。

阻塞模式使用就像传统中的支持一样，比较`简单`，但是`性能`和`可靠性`都`不好`；非阻塞模式正好与之相反。

对于低负载、低并发的应用程序，可以使用`同步阻塞I/O`来提升开发速率和更好的维护性；对于高负载、高并发的（网络）应用，应使用 NIO 的`非阻塞模式`来开发。

区别：
- IO流是阻塞的，NIO流是不阻塞的。
- IO 面向流(Stream oriented)，而 NIO 面向缓冲区(Buffer oriented)。
- NIO 通过Channel（通道） 进行读写。
- NIO有选择器，而IO没有。

# 3. AIO (Asynchronous I/O)

AIO 也就是 NIO 2。

AIO 是异步IO的缩写，虽然 NIO 在网络操作中，提供了非阻塞的方法，但是 NIO 的 IO
行为还是同步的。对于 NIO 来说，我们的业务线程是在 IO
操作准备好时，得到通知，接着就由这个线程自行进行 IO 操作，IO操作本身是同步的。

[详细参考](https://github.com/Snailclimb/JavaGuide/blob/master/docs/java/BIO-NIO-AIO.md)