# 1.异常

## 1.1 异常的产生过程

```java
public class Demo02Exception{
    public static void main(String []args){
        //创建int类型的数组，并赋值
        int [] arr ={1,2,3};
        int e = getElement(arr,3);
        System.out.println(e);
    }
    /*定义一个方法，获取数组指定索引处的元素
    参数：
        int [] arr
        int [] index
        */
    public static int getElement(int[] arr, int index){
        int ele = arr[index];
        return ele;
    }
}
```

![image-20191127224456715]( https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/image-20191127224456715.png )

![20191128_212805]( https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/20191128_212805.png )

## 1.2 throws关键字

<img src="https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-11-29-22-18-13.png" alt="Screenshot_2019-11-29-22-18-13"  />

## 1.3 try_catch异常处理的第二种方式

![Screenshot_2019-11-29-22-35-37](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-11-29-22-35-37.png)

## 1.4 异常注意事项--多异常的捕获处理

![Screenshot_2019-11-30-09-53-08](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-11-30-09-53-08.png)

![Screenshot_2019-11-30-10-00-15](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-11-30-10-00-15.png)

## 1.5 异常注意事项--finally有return语句

![Screenshot_2019-11-30-10-06-41](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-11-30-10-06-41.png)

## 1.6 异常注意事项--子父类异常

![Screenshot_2019-11-30-10-12-05](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-11-30-10-12-05.png)

## 1.7 自定义异常

![Screenshot_2019-11-30-10-20-54](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-11-30-10-20-54.png)

![Screenshot_2019-11-30-10-21-58](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-11-30-10-21-58.png)

# 2、IDEA的复制粘贴快捷键失效解决方法

#### 打开IDEA--->点击Tools， 把Vim Emulator 前面的√去掉就好了，这样复制粘贴的快捷键就恢复正常了。 

# 3、多线程

## 3.1 并发与并行

![Screenshot_2019-11-30-10-48-39](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-11-30-10-48-39.png)

## 3.2 线程与进程

![Screenshot_2019-11-30-11-03-18](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-11-30-11-03-18.png)

## 3.3 进程的概念

![Screenshot_2019-11-30-11-01-06](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-11-30-11-01-06.png)

## 3.4 线程的概念

![Screenshot_2019-11-30-11-11-10](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-11-30-11-11-10.png)

## 3.5 线程调度

![Screenshot_2019-11-30-11-14-46](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-11-30-11-14-46.png)

**分时调度：谁的优先级高，分配的cpu时间更久，例如：线程1、2、3的优先级为（高，中，低），cup运行时间为9秒，那么他们的cup分配时间为：先运行线程一5秒，再运行线程二3秒，最后运行线程三1秒。**

**抢占式调度：随机获取cpu运行，谁的优先级高，获取cup运行的概率越大。**

## 3.6 主线程

![Screenshot_2019-11-30-11-28-44](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-11-30-11-28-44.png)

## 3.7 创建多线程程序的第一种方式

```java
package Demo06.Thread;
/*
    创建多线程程序的第一种方式：创建Thread类的子类
    java.lang.Thread类：是描述线程的类，我们想要实现多线程程序，就必须基础Thread类

    实现步骤：
    1。创建一个Thread类的子类
    2.在Thread类的子类中重写Thread类中的run方法，设置线程任务（开启线程要做什么？）
    3.创建Thread类的子类对象
    4.调用Thread类中的方法start方法，开启新的线程，执行run方法
        void start（）使该线程开始执行；java虚拟机调用该线程的run方法。
        结果是两个线程并发地执行；当前线程（main线程）和另一个线程（创建的新线程，执行其run方法）。
        多次启动一个线程是非法的，特别是当线程已经结束执行后，不能再重写启动。
       java程序属于抢占式调度，哪个线程的优先级高，哪个线程优先执行，随机选择一个执行
 */
public class Demo01Thread {
    public static void main(String[] args) {
        //3.创建Thread类的子类对象
        MyThread mt = new MyThread();
        //4.调用Thread类中的方法start方法，开启新的线程，执行run方法
        mt.start();
        for(int i = 0; i < 20; i++){
            System.out.println("main:"+i);
        }
    }
}

```

```java
package Demo06.Thread;
//1.创建一个Thread类的子类
public class MyThread extends  Thread{
    //2.在Thread类的子类中重写Thread类中的run方法，设置线程任务（开启线程要做什么？）
    @Override
    public void run() {
        for(int i = 0; i < 20; i++){
            System.out.println("run:"+i);
        }
    }

}

```

## 3.8 多线程原理

![Screenshot_2019-11-30-14-35-00](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-11-30-14-35-00.png)

## 3.9 多线程内存图解

![Screenshot_2019-11-30-14-42-47](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-11-30-14-42-47.png)

**<u>当创建了一个Thread对象后，调用run（）方法和调用start（）方法是有区别的，如果用成run（）方法，那么main（）方法压入栈后，继续执行run（）方法，程序从上往下执行，因此是单线程来执行的；而调用start（）方法，则会再新建一个栈内存存run（）方法，此时cpu会执行多个栈里面的方法，此时是多线程执行。</u>**

## 3.10 Thread类的常用方法

```java
package Demo01.getName;
/*
    1.使用Thread中的方法getName（）
        String getName()返回该线程的名称。
    2.可以先获取到当前正在执行的线程，再使用线程中的方法getName（）获取线程的名称
        static Thread currentThread()返回对当前正在执行的线程对象的引用。
 */
//定义一个Thread类的子类
public class MyThread extends Thread{
    //重写Thread类中的run方法，设置线程任务
    @Override
    public void run() {
        //获取当前线程并且获取其名称
        System.out.println(Thread.currentThread().getName());
    }
}


```

```java
package Demo01.getName;
/*
    线程的名称：
        主线程：main
        新线程：Thread-0，Thread-1，Thread-2
 */
public class Demo01Thread {
    public static void main(String[] args) {
        MyThread mt = new MyThread();
        mt.start();
        new MyThread().start();
        new MyThread().start();

        //链式编程
        System.out.println(Thread.currentThread().getName());
    }
}

```

![image-20191130151144079](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191130151144079.png)

**注意主线程main（）没有getName（）的方法，它没有继承Thread类，因此必须用Thread.currentThread（）获得当前的线程。**

## 3.11 设置线程名称

**两种方法：**

![image-20191130153053086](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191130153053086.png)

***方法一：上图中1方法***

```java
package Demo01Thread.setName;

public class MyThread extends Thread{
    @Override
    public void run() {
        System.out.println(Thread.currentThread().getName());
    }
}

```

```java
package Demo01Thread.setName;

public class Demo01Thread {
    public static void main(String[] args) {
        MyThread mt = new MyThread();
        //设置线程的名称
        mt.setName("小明");
        mt.start();
    }
}

```

![image-20191130154431533](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191130154431533.png)

***方法二：图中2方法***

```java
package Demo01Thread.setName;

public class MyThread extends Thread{
    public MyThread(){}
    //构造方法设置名称
    public MyThread(String name){
        super(name);
    }

    @Override
    public void run() {
        System.out.println(Thread.currentThread().getName());
    }
}

```

```java
package Demo01Thread.setName;

public class Demo01Thread {
    public static void main(String[] args) {
        MyThread mt = new MyThread();
        mt.setName("小明");
        mt.start();
        new MyThread("旺财").start();
    }
}

```

![image-20191130154402467](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191130154402467.png)

## 3.12 Thread中的常用方法--sleep（）

![image-20191130154824964](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191130154824964.png)

## 3.13 创建多线程的第二种方式--实现Runnable接口

![image-20191130160222775](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191130160222775.png)

```java
package demo04.Runnable;
//1.创建一个Runnable接口的实现类
public class RunnableImpl implements Runnable{
    //2.在实现类中重写Runnable接口的run方法，设置线程任务
    @Override
    public void run() {
        for(int i=0;i<20;i++){
            System.out.println(Thread.currentThread().getName()+"-->"+i);
        }
    }
}

```

```java
package demo04.Runnable;

public class Demo01Thr {
    public static void main(String[] args) {
        //3.创建一个Runnable接口的实现类对象
        RunnableImpl ra = new RunnableImpl();
        //4.创建Thread类对象，构造方法中传递Runnable接口的实现对象
        Thread t = new Thread(ra);
        //5.调用Thread类中的start方法，开启新的线程执行run方法
        t.start();
        for(int i=0;i<20;i++){
            System.out.println(Thread.currentThread().getName()+"-->"+i);
        }
    }
}

```

## 3.14 Thread和Runnable的区别

![image-20191130161402924](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191130161402924.png)

```java
package demo04.Runnable;
public class RunnableImpl implements Runnable{
    @Override
    public void run() {
        for(int i=0;i<20;i++){
            System.out.println(Thread.currentThread().getName()+"-->"+i);
        }
    }
}
```

````java
package demo04.Runnable;

public class Demo01Thr {
    public static void main(String[] args) {
        RunnableImpl ra = new RunnableImpl();
        //Runnable接口实现对象的，好处，解耦，如：再来一个Runnable对象ra2，其中ra2里的run（）方法中的输出内容不一样，那么可以这样:Thread t = new Thread(ra2),用ra2替换下面new Thread(ra)中的ra，而t.start()则不用改变，达到解耦的目的。
        Thread t = new Thread(ra);
        t.start();
        for(int i=0;i<20;i++){
            System.out.println(Thread.currentThread().getName()+"-->"+i);
        }
    }
}

````

## 3.15 匿名内部类实现多线程

![image-20191130162756387](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191130162756387.png)

继承方式

```java
public class Demo01InnerClassThread{
    public static void main(String []args){
        //线程的父类是Thread
        //new MyThread().start();
        new Thread(){
            //重写run方法，设置线程任务
            @Override
            public void run() {
        		for(int i=0;i<20;i++){
           			 System.out.println(Thread.currentThread().getName()+"-->"+i);
       	 }
    }
}.start();
    }
}
```

接口方式

```java
public class Demo01InnerClassThread{
    public static void main(String []args){
        //线程的接口Runnable
//Runnable r = new RunnableImpl();多态
        Runnable r = new Runnable(){
            //重写run方法，设置线程任务
            @Override
            public void run(){
                 for(int i=0;i<20;i++){
            	System.out.println(Thread.currentThread().getName()+"-->"+i);
        		}
            }
		};
        new Thread(r).start();
    }
}
```

接口简化方式

```java
public class Demo01InnerClassThread{
    public static void main(String []args){
        //线程的接口Runnable
//Runnable r = new RunnableImpl();多态
        new Thread(new Runnable(){
            //重写run方法，设置线程任务
            @Override
            public void run(){
                 for(int i=0;i<20;i++){
            	System.out.println(Thread.currentThread().getName()+"-->"+i);
        		}
            }
		}).start();
    }
}
```

## 3.16 线程安全问题产生的原理

![Screenshot_2019-12-01-09-32-26](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-12-01-09-32-26.png)

## 3.17 解决线程安全问题--同步代码块（第一种方式）

```java
package demo07.Synchronized;
/*
    卖票案例出现了线程安全问题
    卖出了不存在的票和重复的票

    解决线程安全问题的一种方案：使用同步代码块
    格式：
        synchronized（锁对象）{
           可能会出现线程安全问题的代码(访问了共享数据的代码)
        }
    注意：
        1.通过代码块中的锁对象，可以使用任意的对象
        2.但是必须保证多个线程使用的锁对象是同一个
        3.锁对象作用：
            把同步代码块锁住，只让一个线程在同步代码块中执行
 */
public class RunnableImpl implements Runnable{
    //定义一个多个线程共享的票源
    private int ticket = 100;

    //创建一个锁对象，并且该对象必须在run方法的外边，如果在run方法里，那么三个线程将会有三个锁对象，这样就不对，锁对象必须是只有一个
    Object obj = new Object();

    //设置线程任务：买票
    @Override
    public void run() {
        while (true){
            //创建同步代码块
            synchronized (obj){
                if(ticket>0){
                    try {
                        Thread.sleep(10);
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }

                    //票存在，卖票 ticket--
                    System.out.println(Thread.currentThread().getName()+"-->正在卖第"+ticket+"张票");
                    ticket--;
                }
            }
        }
    }
}

```

```java
package demo07.Synchronized;

public class Demo01Ticket {
    public static void main(String[] args) {
        //创建Runnable接口的实现类对象
        RunnableImpl run = new RunnableImpl();
        //创建Thread类对象，构造方法中传递Runnable接口的实现类对象
        Thread t0 = new Thread(run);
        Thread t1 = new Thread(run);
        Thread t2 = new Thread(run);
        //调用start方法开启多线程
        t0.start();
        t1.start();
        t2.start();
    }
}

```

## 3.18 同步技术的原理

![Screenshot_2019-12-01-10-02-58](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/Screenshot_2019-12-01-10-02-58.png)

## 3.19 解决线程安全问题--同步方法（第二种方式）

```java
package demo07.Synchronized;
/*
    卖票案例出现了线程安全问题
    卖出了不存在的票和重复的票

    解决线程安全问题的二种方案：使用同步方法
    使用步骤：
    	1.把访问了共享数据的代码抽取出来，放到一个方法中
    	2.在方法上添加synchronized修饰符
    格式：定义方法的格式
    修饰符 synchronized 返回值类型 方法名（参数列表）{
    	可能会出现线程安全问题的代码（访问了共享数据的代码）
    }    
 */
public class RunnableImpl implements Runnable{
    //定义一个多个线程共享的票源
    private int ticket = 100;

    //创建一个锁对象，并且该对象必须在run方法的外边，如果在run方法里，那么三个线程将会有三个锁对象，这样就不对，锁对象必须是只有一个
    Object obj = new Object();

    //设置线程任务：买票
    @Override
    public void run() {
        while (true){
            payTicket();
        }
    }
    /*
    	定义一个同步方法
    	同步方法也会把方法内部的代码锁住
    	只让一个线程执行
    	同步方法的锁对象是谁？
    	就是实现类对象 new RunnableImpl()
    	也就是this
    */
    public synchronized void payTicket(){
        if(ticket>0){
                    try {
                        Thread.sleep(10);
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }

                    //票存在，卖票 ticket--
                    System.out.println(Thread.currentThread().getName()+"-->正在卖第"+ticket+"张票");
                    ticket--;
                }
	}
}

```

```java
package demo07.Synchronized;

public class Demo01Ticket {
    public static void main(String[] args) {
        //创建Runnable接口的实现类对象
        RunnableImpl run = new RunnableImpl();
        //创建Thread类对象，构造方法中传递Runnable接口的实现类对象
        Thread t0 = new Thread(run);
        Thread t1 = new Thread(run);
        Thread t2 = new Thread(run);
        //调用start方法开启多线程
        t0.start();
        t1.start();
        t2.start();
    }
}

```

## 3.20 静态同步方法

```java
package demo07.Synchronized;

public class RunnableImpl implements Runnable{
    //这里的ticket必须加上static，因为调用的方法是静态的
    private static int ticket = 100;

    Object obj = new Object();

    
    @Override
    public void run() {
        while (true){
            payTicket();
        }
    }
    /*
    	静态的同步方法
    	锁对象是谁？
    	不能是this
    	this是创建对象之后产生的，静态方法优先与对象
    	静态方法的锁对象是本类的class属性-->class文件对象（反射）本例中为(RunnableImpl.class)
    */
    public static synchronized void payTicket(){
        if(ticket>0){
                    try {
                        Thread.sleep(10);
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }

                   
                    System.out.println(Thread.currentThread().getName()+"-->正在卖第"+ticket+"张票");
                    ticket--;
                }
	}
}

```

```java
package demo07.Synchronized;

public class Demo01Ticket {
    public static void main(String[] args) {
        //创建Runnable接口的实现类对象
        RunnableImpl run = new RunnableImpl();
        //创建Thread类对象，构造方法中传递Runnable接口的实现类对象
        Thread t0 = new Thread(run);
        Thread t1 = new Thread(run);
        Thread t2 = new Thread(run);
        //调用start方法开启多线程
        t0.start();
        t1.start();
        t2.start();
    }
}

```

## 3.21 解决线程安全问题--Lock锁（第三种方式）

![image-20191201114954985](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201114954985.png)

```java
package demo07.Synchronized;

public class RunnableImpl implements Runnable{
    
    private int ticket = 100;

    //1.在成员位置创建一个ReentrantLock对象
	Lock l = new ReentrantLock();
    
    @Override
    public void run() {
        while (true){
            //2.在可能会出现安全问题的代码前调用Lock接口中的方法lock获取锁
            l.lock();
            if(ticket>0){
                    try {
                        Thread.sleep(10);
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
          System.out.println(Thread.currentThread().getName()+"-->正在卖第"+ticket+"张票");
                    ticket--;
                }
            //3.在可能会出现安全问题的代码后调用Lock接口中的方法unlock释放锁
            l.unlock();
        }
    }
}

```

```java
package demo07.Synchronized;

public class Demo01Ticket {
    public static void main(String[] args) {
        //创建Runnable接口的实现类对象
        RunnableImpl run = new RunnableImpl();
        //创建Thread类对象，构造方法中传递Runnable接口的实现类对象
        Thread t0 = new Thread(run);
        Thread t1 = new Thread(run);
        Thread t2 = new Thread(run);
        //调用start方法开启多线程
        t0.start();
        t1.start();
        t2.start();
    }
}
```

<u>下面是提高程序效率的写发</u>：**将l.unlock()放在finally代码块中**

```java
package demo07.Synchronized;

public class RunnableImpl implements Runnable{
    
    private int ticket = 100;

    //1.在成员位置创建一个ReentrantLock对象
	Lock l = new ReentrantLock();
    
    @Override
    public void run() {
        while (true){
            //2.在可能会出现安全问题的代码前调用Lock接口中的方法lock获取锁
            l.lock();
            if(ticket>0){
                    try {
                        Thread.sleep(10);                  					       System.out.println(Thread.currentThread().getName()+"-->正在卖第"+ticket+"张票");
                    ticket--;
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }finally{
                        //3.在可能会出现安全问题的代码后调用Lock接口中的方法unlock释放锁
            			l.unlock();
                    }
                }
        }
    }
}

```

```java
package demo07.Synchronized;

public class Demo01Ticket {
    public static void main(String[] args) {
        //创建Runnable接口的实现类对象
        RunnableImpl run = new RunnableImpl();
        //创建Thread类对象，构造方法中传递Runnable接口的实现类对象
        Thread t0 = new Thread(run);
        Thread t1 = new Thread(run);
        Thread t2 = new Thread(run);
        //调用start方法开启多线程
        t0.start();
        t1.start();
        t2.start();
    }
}
```

# 4、等待唤醒机制

## 4.1 线程状态

![image-20191201123617313](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201123004287.png)

## 4.2 线程之间的通信--等待唤醒案例

*<u>**wait()和sleep()方法是不一样的：wait是object的方法，sleep是thread的方法，wait和sleep都可以设置时间，但是只有wait可以不设置时间，进入无线等待状态，当别的线程调用Object.notify()方法是才唤醒**</u>*

![image-20191201123617313](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201123617313.png)

![image-20191201144949885](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201144949885.png)

```java
package demo10.WaitAndNotify;

public class Demo01WaitAndNotify {
    public static void main(String[] args) {
        Object obj = new Object();

        //创建一个顾客线程
        new Thread(){
            @Override
            public void run() {
                synchronized (obj){
                    System.out.println("告知老板要的包子的种类和数量");
                    try {
                        obj.wait();
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                    System.out.println("包子已经做好了，开吃");
                }
            }
        }.start();

        //创建一个老板线程
        new Thread(){
            @Override
            public void run() {
                //花了5秒做包子
                try {
                    Thread.sleep(5000);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
                synchronized (obj){
                    System.out.println("包子做好了，告知顾客可以吃包子了");
                    obj.notify();
                }
            }
        }.start();
    }
}

```

![image-20191201151405940](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201151405940.png)

**等了5秒后<u>*“包子做好了…”*</u>这些话才打印出来**

## 4.3 object类中wait带参方法和notifyAll方法

![image-20191201152237858](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201152237858.png)

# 5.线程池

## 5.1 线程池的概念和原理

![image-20191201161705235](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201161705235.png)

![image-20191201161754757](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201161754757.png)

## 5.2 线程池的代码实现

![image-20191201162411641](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201162411641.png)

![image-20191201162758754](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201162758754.png)

![image-20191201162833308](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201162833308.png)

# 6、lambda表达式

## 6.1 使用lambda表达式解决创建线程对象的冗余操作

![image-20191201164053261](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201164053261.png)

## 6.2 lambda表达式的标准格式

![image-20191201164502950](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201164502950.png)

## 6.3 lambda表达式的无参无返回值例子

![image-20191201165027736](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201165027736.png)

![image-20191201165106202](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201165106202.png)

## 6.4 lambda表达式的有参有返回值例子

<u>**用匿名内部类：**</u>

![image-20191201165636596](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201165636596.png)

<u>**用lambda表达式：**</u>

![image-20191201165742462](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201165742462.png)

## 6.5 lambda表达式省略格式

![image-20191201171259768](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201171259768.png)

**<u>*省略前：</u>***

![image-20191201171343734](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201171343734.png)

**<u>省略后：</u>**

![image-20191201171430457](https://raw.githubusercontent.com/mzxssg/studyJava/master/picture/Screenshots/image-20191201171430457.png)