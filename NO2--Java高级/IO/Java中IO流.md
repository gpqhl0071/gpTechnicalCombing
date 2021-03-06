# Java 中 IO 流分为几种?

- 按照流的流向分，可以分为输入流和输出流；
- 按照操作单元划分，可以划分为字节流和字符流；
- 按照流的角色划分为节点流和处理流。

Java Io流共涉及40多个类，这些类看上去很杂乱，但实际上很有规则，而且彼此之间存在非常紧密的联系， Java I0流的40多个类都是从如下4个抽象类基类中派生出来的。

- InputStream/Reader: 所有的输入流的基类，前者是字节输入流，后者是字符输入流。
- OutputStream/Writer: 所有输出流的基类，前者是字节输出流，后者是字符输出流。

![1.png](http://ww1.sinaimg.cn/large/9b13c8fdly1g8n4kewjo1j20hm0qu12d.jpg)

按操作对象分类结构图： 

![2.jpg](http://ww1.sinaimg.cn/large/9b13c8fdly1g8lz65787nj20k00ev0tp.jpg)

## 不管是文件读写还是网络发送接收，信息的最小存储单元都是字节，那为什么 I/O 流操作要分为字节流操作和字符流操作呢？

回答：字符流是由 Java 虚拟机将字节转换得到的，问题就出在这个过程还算是非常耗时，并且，如果我们不知道编码类型就很容易出现乱码问题。所以， I/O 流就干脆提供了一个直接操作字符的接口，方便我们平时对字符进行流操作。如果音频文件、图片等媒体文件用字节流比较好，如果涉及到字符的话使用字符流比较好。 

(https://stackoverflow.com/questions/46874783/byte-stream-vs-character-stream-in-java)[https://stackoverflow.com/questions/46874783/byte-stream-vs-character-stream-in-java]

## Java中I / O类的层次结构

[详细参考](https://user-images.githubusercontent.com/2780145/34911563-14813348-f8f3-11e7-87ef-4c8f589bbdf5.png)


![](https://user-images.githubusercontent.com/2780145/34911563-14813348-f8f3-11e7-87ef-4c8f589bbdf5.png)