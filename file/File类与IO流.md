# 一、File类

## 1.1 File类的概述：![image-20191202210102577](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202210102577.png)

## 1.2 File类的静态成员变量

![image-20191202210748860](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202210748860.png)

## 1.3 绝对路径和相对路径

![image-20191202211401978](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202211401978.png)

## 1.4 File类的构造方法

**构造方法一：**

![image-20191202212157477](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202212157477.png)

**构造方法二：**

![image-20191202212333640](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202212333640.png)

**构造方法三：**

![image-20191202212432316](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202212432316.png)

## 1.5 File类获取功能的方法

![image-20191202213503263](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202213503263.png)

**方法一：getAbsolutePath()**

![image-20191202213437882](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202213437882.png)

**方法二：getPath()**

![image-20191202214015408](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202214015408.png)

**方法三：getName()**

![image-20191202214218086](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202214218086.png)

**方法四：length()**

![image-20191202214541271](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202214541271.png)

## 1.6 File类判断功能的方法

![image-20191202214705266](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202214705266.png)

**方法一：exist（）方法**

![image-20191202215109573](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202215109573.png)

**方法二：isDirectory（）方法和方法三：isFile（）方法**

![image-20191202215627642](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202215627642.png)

![image-20191202215715481](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202215715481.png)

## 1.7File类创建删除功能的方法

![image-20191202215846421](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202215846421.png)

**方法一：creatNewFile():**

![image-20191202220431150](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202220431150.png)



**方法二：delete():**

![image-20191202221701102](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202221701102.png)

**方法三mkdir()和方法四mkdirs():**

![image-20191202221025380](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202221025380.png)

![image-20191202221350609](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202221350609.png)

## 1.8 File类遍历（文件夹）目录功能

![image-20191202221931076](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202221931076.png)

**方法一：list()**:

![image-20191202222232699](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202222232699.png)

![image-20191202222523165](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202222523165.png)

**方法二：listFiles():**

![image-20191202222447505](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202222447505.png)

![image-20191202222505194](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191202222505194.png)

# 二、递归

## 2.1 递归概念&分类&注意事项

![image-20191203201018732](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191203201018732.png)

**没有限制条件为什么会溢出**

![image-20191203201117298](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191203201117298.png)

**有限制条件，但是递归次数也不能太多，否则也会溢出**

![image-20191203201307962](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191203201307962.png)

![image-20191203201351774](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191203201351774.png)

## 2.2 使用递归计算1~n之间的和

![image-20191203202429148](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191203202429148.png)

## 2.3 递归打印多级目录

![image-20191203203638174](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191203203638174.png)

![image-20191203203659682](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191203203659682.png)

## 2.4 文件搜索

**只打印出以.java结尾的文件**

![image-20191203204313826](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191203204313826.png)

**如果结尾.java是大写的.JAVA,那么可以先把大写转为小写先：**（加上

```java
s = s.toLowerCase()
```

**这句代码即可**

）

![image-20191203204532509](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191203204532509.png)

**简单写法：(链式写法)**

![image-20191203204815802](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191203204815802.png)

# 三、过滤器

## 3.1 FileFilter过滤器的原理和使用

**还是对上一个方法来改进：**

![image-20191203210603012](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191203210603012.png)

**使用FileFilter接口：**

![image-20191203210706922](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191203210706922.png)

![image-20191203210758645](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191203210758645.png)

**原理：**

![image-20191203210838459](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191203210838459.png)

**使用FileNameFilter接口：**

![image-20191203211715517](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191203211715517.png)

![image-20191203211846797](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191203211846797.png)

# 四、IO流

## 4.1 IO概述

![image-20191204214835884](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191204214835884.png)

## 4.2 字节输出流OutputStream

![image-20191204220436967](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191204220436967.png)

## 4.3 字节输出流写入数据到文件

![image-20191204221354543](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191204221354543.png)

## 4.4 文件存储的原理和记事本打开文件的样式

![image-20191204222059710](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191204222059710.png)

## 4.5 字节输出流写多个字节的办法

![image-20191204223355274](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191204223355274.png)

![image-20191204223501717](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191204223501717.png)

![image-20191204223542098](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191204223542098.png)

## 4.6 字节输出流的续写和换行

![image-20191204224223617](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191204224223617.png)

![image-20191204224250675](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191204224250675.png)

## 4.7 字节输入流InputStream和FileInputStream

![image-20191204225008976](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191204225008976.png)

## 4.8 字节输入流读取字节数据

![image-20191204230338378](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191204230338378.png)

![image-20191204230402773](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191204230402773.png)

![image-20191204230458966](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191204230458966.png)

**注意：<u>不能写如下格式：</u>**

![image-20191204230655549](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191204230655549.png)

![image-20191204230708869](https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191204230708869.png)

**控制台打印错误!原因如下：**

<u>fis.read()先读到了97，但没打印，system里面读到了98并打印了98，while里fis.read()再读到99，但是没有打印，system里面读到了-1并打印了-1，因为文件没数据了。因此得用个变量存起来</u>

## 4.9 字节输入流一次读取多个字节

![image-20191206085848501]( https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191206085848501.png)

![image-20191206085811353]( https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191206085811353.png)

![image-20191206085901803]( https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191206085901803.png)

![image-20191206090034263]( https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191206090034263.png)

## 4.10 练习__文件复制

![image-20191206092027618]( https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191206092027618.png)

![image-20191206093130620]( https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191206093130620.png)

```JAVA
package IOAndProperties;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;

public class Demo03CopyFile {
    public static void main(String[] args) throws IOException {
        //1、创建一个字节输入流对象，构造方法中绑定要读取的数据源
        FileInputStream fls = new FileInputStream("D:\\个人简历.docx");
        //2.创建一个字节输入出流对象，构造方法中绑定要写入的目的地
        FileOutputStream fos = new FileOutputStream("E:\\个人简历.docx");
        //一次读取一个字节写入一个字节的方式
        //3.使用字节输入流对象中的方法read读取文件
        /*int len = 0;
        while((len = fls.read())!=-1){
            //4.使用字节输出流中的方法write，把读取到的字节写入到目的地的文件中
            fos.write(len);
        }*/
        //使用数组缓冲读取多个字节，写入多个字节
        int len = 0;
        byte[] bytes = new byte[1024];
        while((len = fls.read(bytes))!=-1){
            //4.使用字节输出流中的方法write，把读取到的字节写入到目的地的文件中
            fos.write(bytes,0,len);
        }
        //5.释放资源（先关写的，后关闭读的，如果写完了，肯定读取完毕了
        fos.close();
        fls.close();
    }
}

```

# 5、字符输入流

## 5.1 字符输入流Reader类和FileReader类

![image-20191206102204106]( https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191206102204106.png)

## 5.2 字符输入流读取字符数据

![image-20191206102805095]( https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191206102805095.png)

## 5.3 字符输出流Writer类和FileWriter类

![image-20191206105241558]( https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191206105241558.png)

## 5.4 字符输出流的基本使用

![image-20191206105929739]( https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191206105929739.png)

**注意字符输出流是先把数据存到缓冲去的，如果没调用flush方法，不会写入到文件中去，或者调用close方法也会先把数据从缓冲区放到文件中去，再关闭流。**

## 5.5 flush方法和close方法的区别

![image-20191206110354123]( https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191206110354123.png)

![image-20191206110414174]( https://raw.githubusercontent.com/mzxssg/studyJava/master/file/picture/Screenshots/image-20191206110414174.png)