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