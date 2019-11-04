通常情况下，我们创建的变量是可以被任何一个线程访问并修改的。如果想实现每一个线程都有自己的专属本地变量该如何解决呢？ JDK中提供的ThreadLocal类正是为了解决这样的问题。 ThreadLocal类主要解决的就是让每个线程绑定自己的值，可以将ThreadLocal类形象的比喻成存放数据的盒子，盒子中可以存储每个线程的私有数据。

如果你创建了一个ThreadLocal变量，那么访问这个变量的每个线程都会有这个变量的本地副本，这也是ThreadLocal变量名的由来。他们可以使用 get（） 和 set（） 方法来获取默认值或将其值更改为当前线程所存的副本的值，从而避免了线程安全问题。



```java
public class Demo {

  public static class MyRunnable implements Runnable {

    private ThreadLocal<Integer> threadLocal = new ThreadLocal<Integer>();
    private int num = 0;

    @Override
    public void run() {
      threadLocal.set((int) (Math.random() * 100D));
      num = (int) (Math.random() * 100D);
      try {
        Thread.sleep(2000);
      } catch (InterruptedException e) {
      }

      System.out.println(threadLocal.get());
      System.out.println("num = " + num);
    }
  }


  public static void main(String[] args) {
    MyRunnable sharedRunnableInstance = new MyRunnable();

    Thread thread1 = new Thread(sharedRunnableInstance);
    Thread thread2 = new Thread(sharedRunnableInstance);

    thread1.start();
    thread2.start();

    try {
      thread1.join(); //wait for thread 1 to terminate
      thread2.join(); //wait for thread 2 to terminate
    } catch (InterruptedException e) {
      e.printStackTrace();
    }
  }

}
```