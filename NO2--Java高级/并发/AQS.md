# AQS简介

AQS：AbstractQueuedSynchronizer，即队列同步器。它是构建锁或者其他同步组件的基础框架（如ReentrantLock、ReentrantReadWriteLock、Semaphore等），JUC并发包的作者（Doug Lea）期望它能够成为实现大部分同步需求的基础。它是JUC并发包中的核心基础组件。

AQS解决了大量细节问题，例如获取同步状态、FIFO同步队列。基于AQS来构建同步器可以带来很多好处。它不仅能够极大地减少实现工作，而且也不必处理在多个位置上发生的竞争问题。

参考：[https://juejin.im/entry/5ae02a7c6fb9a07ac76e7b70](https://juejin.im/entry/5ae02a7c6fb9a07ac76e7b70)

**AQS主要做三件事：** 

- 同步状态管理
- 线程阻塞和唤醒
- 维护同步队列



参考：[https://programmer.group/detailed-java-lock-queue-synchronizer-aqs.html](https://programmer.group/detailed-java-lock-queue-synchronizer-aqs.html)

# CLH同步队列

CLH同步队列是一个FIFO双向队列，AQS依赖它来完成同步状态的管理，当前线程如果获取同步状态失败时，AQS则会将当前线程已经等待状态等信息构造成一个节点（Node）并将其加入到CLH同步队列，同时会阻塞当前线程，当同步状态释放时，会把首节点唤醒（公平锁），使其再次尝试获取同步状态。

在CLH同步队列中，一个节点表示一个线程，它保存着线程的引用（thread）、状态（waitStatus）、前驱节点（prev）、后继节点（next）

