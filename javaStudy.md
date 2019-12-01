# 1.异常

## 异常的产生过程

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

## throws关键字

<img src="E:\githubFile\studyJava\picture\Screenshots\Screenshot_2019-11-29-22-18-13.png" alt="Screenshot_2019-11-29-22-18-13"  />

## try_catch异常处理的第二种方式

![Screenshot_2019-11-29-22-35-37](E:\githubFile\studyJava\picture\Screenshots\Screenshot_2019-11-29-22-35-37.png)

## 异常注意事项--多异常的捕获处理

![Screenshot_2019-11-30-09-53-08](E:\githubFile\studyJava\picture\Screenshots\Screenshot_2019-11-30-09-53-08.png)

![Screenshot_2019-11-30-10-00-15](E:\githubFile\studyJava\picture\Screenshots\Screenshot_2019-11-30-10-00-15.png)

## 异常注意事项--finally有return语句

![Screenshot_2019-11-30-10-06-41](E:\githubFile\studyJava\picture\Screenshots\Screenshot_2019-11-30-10-06-41.png)

## 异常注意事项--子父类异常

![Screenshot_2019-11-30-10-12-05](E:\githubFile\studyJava\picture\Screenshots\Screenshot_2019-11-30-10-12-05.png)

## 自定义异常

![Screenshot_2019-11-30-10-20-54](E:\githubFile\studyJava\picture\Screenshots\Screenshot_2019-11-30-10-20-54.png)

![Screenshot_2019-11-30-10-21-58](E:\githubFile\studyJava\picture\Screenshots\Screenshot_2019-11-30-10-21-58.png)

# 2、IDEA的复制粘贴快捷键失效解决方法

#### 打开IDEA--->点击Tools， 把Vim Emulator 前面的√去掉就好了，这样复制粘贴的快捷键就恢复正常了。 

# 3、多线程

## 并发与并行

![Screenshot_2019-11-30-10-48-39](E:\githubFile\studyJava\picture\Screenshots\Screenshot_2019-11-30-10-48-39.png)

## 线程与进程

![Screenshot_2019-11-30-11-03-18](E:\githubFile\studyJava\picture\Screenshots\Screenshot_2019-11-30-11-03-18.png)

## 进程的概念

![Screenshot_2019-11-30-11-01-06](E:\githubFile\studyJava\picture\Screenshots\Screenshot_2019-11-30-11-01-06.png)

## 线程的概念

![Screenshot_2019-11-30-11-11-10](E:\githubFile\studyJava\picture\Screenshots\Screenshot_2019-11-30-11-11-10.png)

## 线程调度

![Screenshot_2019-11-30-11-14-46](E:\githubFile\studyJava\picture\Screenshots\Screenshot_2019-11-30-11-14-46.png)

**分时调度：谁的优先级高，分配的cpu时间更久，例如：线程1、2、3的优先级为（高，中，低），cup运行时间为9秒，那么他们的cup分配时间为：先运行线程一5秒，再运行线程二3秒，最后运行线程三1秒。**

**抢占式调度：随机获取cpu运行，谁的优先级高，获取cup运行的概率越大。**

## 主线程

![Screenshot_2019-11-30-11-28-44](E:\githubFile\studyJava\picture\Screenshots\Screenshot_2019-11-30-11-28-44.png)

## 创建多线程程序的第一种方式

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

## 多线程原理

![Screenshot_2019-11-30-14-35-00](E:\githubFile\studyJava\picture\Screenshots\Screenshot_2019-11-30-14-35-00.png)

## 多线程内存图解

![Screenshot_2019-11-30-14-42-47](E:\githubFile\studyJava\picture\Screenshots\Screenshot_2019-11-30-14-42-47.png)

**<u>当创建了一个Thread对象后，调用run（）方法和调用start（）方法是有区别的，如果用成run（）方法，那么main（）方法压入栈后，继续执行run（）方法，程序从上往下执行，因此是单线程来执行的；而调用start（）方法，则会再新建一个栈内存存run（）方法，此时cpu会执行多个栈里面的方法，此时是多线程执行。</u>**

## Thread类的常用方法

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

![image-20191130151144079](E:\githubFile\studyJava\picture\Screenshots\image-20191130151144079.png)

**注意主线程main（）没有getName（）的方法，它没有继承Thread类，因此必须用Thread.currentThread（）获得当前的线程。**

## 设置线程名称

**两种方法：**

![image-20191130153053086](E:%5CgithubFile%5CstudyJava%5Cpicture%5CScreenshots%5Cimage-20191130153053086.png)

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

![image-20191130154431533](E:%5CgithubFile%5CstudyJava%5Cpicture%5CScreenshots%5Cimage-20191130154431533.png)

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

![image-20191130154402467](E:%5CgithubFile%5CstudyJava%5Cpicture%5CScreenshots%5Cimage-20191130154402467.png)

## Thread中的常用方法--sleep（）

![image-20191130154824964](E:%5CgithubFile%5CstudyJava%5Cpicture%5CScreenshots%5Cimage-20191130154824964.png)

## 创建多线程的第二种方式--实现Runnable接口

![image-20191130160222775](E:%5CgithubFile%5CstudyJava%5Cpicture%5CScreenshots%5Cimage-20191130160222775.png)

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

## Thread和Runnable的区别

![image-20191130161402924](E:%5CgithubFile%5CstudyJava%5Cpicture%5CScreenshots%5Cimage-20191130161402924.png)

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

## 匿名内部类实现多线程

![image-20191130162756387](E:%5CgithubFile%5CstudyJava%5Cpicture%5CScreenshots%5Cimage-20191130162756387.png)

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

