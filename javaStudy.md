# 1.异常

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

# 2、IDEA的复制粘贴快捷键失效解决方法

#### 打开IDEA--->点击Tools， 把Vim Emulator 前面的√去掉就好了，这样复制粘贴的快捷键就恢复正常了。 

