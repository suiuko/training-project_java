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



