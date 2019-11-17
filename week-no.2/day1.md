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



