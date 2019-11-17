# Day1

## 数组

数组就是存储数据长度固定的容器，保证多个数据的数据类型要一致。

#### 数组的定义

格式：

```java
// 第一种方法
数组存储的数据类型 [] 数组名字 = new 数组存储的数据类型 [长度];


//第二种方法
数据类型 [] 数组名 = new 数据类型[]{元素1，元素2，元素3....} 


//第三种方法
数据类型 [] 数组名 = {元素1，元素2，元素3...}
```

### 使用数组

1. 数组长度:数组名.length ，可以获取到数组长度。
2. 数组下标:数组为每个储存空间分配了一个编号，即数组下标

   特点:从零开始，最大为数组长度-1.

3. 数组元素:数组中每个 存储空间 都称为数组元素
4. 元素访问:对每个元素进行赋值或取值的操作
5. 通过下标访问元素， 语法 数组名\[下标\];

   赋值 a\[0\]=10 取值 a=b\[10\]

| 数据类型 | 默认值 |
| :--- | :--- |
| 整数 | 0 |
| 浮点数 | 0.0 |
| char | '\u0000'或空字符'' |
| boolean | false |
| 引用类型 | null（空） |

#### 数组的访问

索引：每一个存储到数组的元素，都会自动的拥有一个编号，从0开始，这个自动编号称为数组索引\(index\)，可以通过数组的索引访问到数组中的元素。

```java
数组名 [索引]
```

_数组的长度属性：每一个数组都具有长度，而且是固定的，java中可以获取到数组的长度。 使用： 数组名.length ,属性length的执行结果是数组的长度，int类型结果。由次可以推断出，数组的最大索引值为 数组名.length-1_

#### 索引访问数组中的元素

```java
数组名 [索引] = 数值，为数组中的元组赋值

变量 = 数组名[索引]，获取出数组中的元素
```

#### 数组原理内存图

java虚拟机要运行程序，必须要对内存进行空间的分配和管理

**java虚拟机的内存划分**

JVM的内存划分：

| 区域名称 | 作用 |
| :--- | :--- |
| 寄存器 | 给CPU使用 |
| 本地方法栈 | JVM在使用操作系统功能的时候使用， |
| 方法区 | 存储可以运行的class文件。 |
| 堆内存 | 存储对象或者数组，new来创建的，都存储在堆内存 |
| 方法栈 | 方法运行时使用的内存，如：main方法运行，进行方法栈中执行。 |

```java
int [] arr2 = new int[3];
System.out.println(arr);

//输出；I@3cd1a2f1
```

## 数组的常见操作

#### 数组越界异常

```java
public static void main(String[] args){
  int [] arr = {1,2,3};
  System.out.println(arr[3]);
}

//越界抛出异常
```

#### 数组空指针异常

```java
public static void main(String[] args){
    int [] arr ={1,2,3};
    arr = null;
System.out.println(arr[0]);
}

arr = null ---->意味着变量arr将不会在保存数组的内存地址，也就不允许在操作数组了。
```

#### 数组遍历

```java
public static void printArray(int[] array){
    for(int i = 0;i<array.length;i++){
    System.out.println(array[i]+ " ");
    }
}
```

```java
数组遍历的一种方法：
for (int i:temp){
    System.out.print(i)
}

```

## 数组作为方法参数和返回值

**数组作为方法参数**

数组作为方法参数传递，传递的参数是数组内存的地址。

```java
public static void main(String[] args){
  int [] arr={1,3,5,7,9};
  printarray(arr);
}

public static void printarray(arr){
  for(int i =0;i<arr.length;i++){
    System.out.println(arr[i])
  }
}
```

**数组作为方法返回值**

数组作为方法的返回值，返回的是数组的内存地址

```java
public static void mian(){
int []arr =getarray();
  for(int i =0;i<arr.length;i++){
    System.out.println(arr[i]);
  }
}

public static int[] getarray(){
int [] arr = {1,2,3,4};
//返回数组的地址，返回到调用者
return arr
}
```

### 数组扩容

原理:

1. 先创建一个长度更长的数组
2. 把旧数组里的数据——拷贝到新数组
3. 把新数组的地址赋值给旧数组

方法：

```java
class Test {
    public static void main(String[] args)
    {
        int[] a ={1,2,3};
        int[] b = new int[a.length*2];//创建长度更大的新数组
        for(int i=0;i<a.length;i++) 
        {
            b[i]=a[i];//将旧数组数据赋值给新数组 
        }
        a = b;//新数组b地址赋值给旧数组a，a也指向了新数组
        }
}
```

```java
class Test {
    public static void main(String[] args)
    {
        int[] a ={1,2,3};
        int[] b = new int[a.length*2];//创建长度更大的新数组
       //arraycopy(旧数组名,复制的起始下标，新数组名， 储存的起始下标，复制长度)
       System
              
         
        }
}
```

```java
class Test {
    public static void main(string[] args)
    {
    int [] a ={1,2,3};
    //使用工具类，创建一个新数组，自动将a值复制并返回一个数组
    //copyOf（旧数组名，数组长度）
    int [] b=java.util.Arrays.copyOf(a,a.length*2);
    a= b;
    }
}
```

随堂练习：定义一个函数，此函数功能用来给数组扩容，接受一个需扩容的数组，返回扩容的数组

```java
class Test {
        public static void main(String[] args)
        {
        int[] a = {1,15,26,23,30,156}; 
        a = ArrayBoom(a);
        for(int i=0;i<a.length;i++)
        {
                System.out.println(a[i]); }
            }
    public static int[] ArrayBoom(int[] a)
    {
        int[] b = new int[a.length*2]; 
        for(int i=0;i<a.length;i++)
        {
        b[i]=a[i]; 
        }
        return b; 
        }
}
```

## 常见排序算法

### 冒泡排序

每次冒泡对相邻两个元素的值比较大小，根据需求决定是否互换位置。

```java
class Test
{
    public static void main(String[] args)
    {
        int[] a ={9,3,6,1,7,4};
        //对数组a进行冒泡排序，升序 ----> 1，3，4，6，7，9
        //相邻元素比较大小，若左边大于右边，则互换位置
        /*
        数组下标      0 1 2 3 4 5
        数组原本排序  9 3 6 1 7 4
        
        第一次冒泡
        0-1     3 9 6 1 7 4
        1-2     3 6 9 1 7 4
        2-3     3 6 1 9 7 4
        3-4     3 6 1 7 4 9
        4-5     3 6 1 7 4 9
        第一次冒泡，下标5是最大值
        
        第二次冒泡
        0-1     3 6 1 7 4 9
        1-2     3 1 6 7 4 9
        2-3     3 1 6 7 4 9
        3-4     3 1 6 4 7 9
        经过第一次冒泡，下标5已经是最大值，不用进行比较，将第二大值，放到倒数第二值
        
        第三次冒泡
        0-1     1 3 6 4 7 9
        1-2     1 3 6 4 7 9
        2-3     1 3 4 6 7 9
        将第三大放在下标3位置上
        
        第四次冒泡
        0-1     1 3 4 6 7 9
        1-2     1 3 4 6 7 9
        经过前三次冒泡，下标5和4和3已经有相应的最大值，不需要后续比较
        第四次冒泡，将第四大值放到下标2位置上。
        
        第五次冒泡
        0-1     1 3 4 6 7 9
        将第五大值放到下标1位置上。
        
        总结：总共冒泡5次，即数组长度-1次
        */
        
        //第一层for循环用来控制冒泡次数
        for(int i = 1;i < a.length;i++)
            {
            //第二层for循环用来控制相邻元素比较
            for(int j =0;j < a.length-i;j++)
            {
                if(a[j]>a[j+1])
                {
                int c = a[j+1];
                a[j+1]=a[j];
                a[j]=c;
                }
            }
        }
        
        //遍历输出
        for(int i=0;i<a.length;i++)
        {
        System.out.println(a[i]);
        }
    }
}
```

### 选择排序

固定一个元素和其他元素进行比较，若固定元素大于其他元素，互换位置。

```java
//对数组a进行选择排序，升序 --->1，3，4，6，7，9
    //选择排序，每次选择都固定一个元素，用来和其他元素进行比较
    //若固定元素大于其他元素，互换位置
    /*
    数组下标 0 1 2 3 4 5 
    数组原本顺序 9 3 6 1 7 4
    
    第一次选择
    0-1 3 9 6 1 7 4
    0-2 3 9 6 1 7 4
    0-3 1 9 6 3 7 4
    0-4 1 9 6 3 7 4
    0-5 1 9 6 3 7 4 
    
    将最小值放入第一个元素位置(下标0)
    
    第二次选择
    1-2 1 6 9 3 7 4 
    1-3 1 3 9 6 7 4 
    1-4 1 3 9 6 7 4 
    1-5 1 3 9 6 7 4 
    
    将第二小值放入下标1
    
    第三次选择
    2-3 1 3 6 9 7 4 
    2-4 1 3 6 9 7 4 
    2-5 1 3 4 9 7 6 
   
    将第三小值放入下标2
    
    第四次选择
    3-4 1 3 4 7 9 6 
    3-5 1 3 4 6 9 7 
    
    将第四小值放入下标3
    
    第五次选择
    4-5 1 3 4 6 7 9 
    将第五小值放入下标4 此时数组中只剩一个元素，即最大值，放入下标5
    
    总结:总共选择了5次，即数组长度-1次 
    代码实现:使用双重for循环实现
    
    1. 第一层for循环，用来指定固定元素，循环变量充当数组
    for(int i=0;i<a.length-1;i++)
    
    2. 第二次for循环，来指定其他元素，循环变量充当数组下
    for(int j=i+1;j<a.length;j++) */
    
    //选择排序 
    //双重for循环
    //第一层for循环，用来指定固定元素，循环变量充当数组下标 
    for(int i=0;i<a.length-1;i++)
    {
    //第二层for循环，来指定其他元素，循环变量充当数组下标
       for(int j=i+1;j<a.length;j++) {
        if(a[i]>a[j])
        {
         int c = a[j]; 
         a[j]=a[i]; 
         a[i]=c;
         } 
       }
       //遍历输出
       for(int i =0;i<a.length;i++)
       {
       System.out.println(a[i]);
       }
    }
```

### JDK 排序

由JDK提供的排序功能，只能升序排序

`java.util.Arrays.sort(数组名);`

```java
import java.util.Arrays;
class Test
{
    public static void main(String[] args)
    {
        int [] a={2,6,9,3,23,5,45};
        java.util.Arrays.sort(a);
        //遍历输出
        for()int i =0;i<a.length;i++
        {
            System.out.println(a[i]);
        }
    }
}
        
```

