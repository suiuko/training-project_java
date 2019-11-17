# Day3

## 循环 -- 流程控制

break ： 跳出switch、循环结构

```java
class TestBreak{
	public static void main(String[] args){
		for(int i=1;i<=10;i++){
			if(i==5){
				//跳出、终止当前循环
				break;
			}
			System.out.println("当前循环次数"+i);
		}
		System.out.println("循环结束");
	}
}
```

执行结果：

continue ： 

```java
class TestContinue{
	public static void main(String[] args){
		for(int i=1;i<=10;i++){
			if(i==5){
				continue;
			}
			System.out.println("当前循环次数"+i);
		}
		System.out.println("循环结束");
	}
}
```

执行结果：

* 注意：break和continue只会对直接包含它们的循环结构起作用

## 局部变量

概念：定义在函数内部的变量，必须先赋值，再使用

作用范围：从定义变量的那一行开始，到定义变量所在代码块的结束

注意：作用范围重合内，不能命名冲突（重复）

```java
class Test1{
	public static void main(String[] args){
        int a = 10;
        if(true){
            int b = 20;
            System.out.println(a);
            System.out.println(b);
        }
    }
}
class Test2{
    public static void main(String[] args){
        int a;
        int b =10;
        if(true){
            //int b = 20;//作用范围重合内，变量名重复
            System.out.println(a);//尚未初始化变量a
            System.out.println(b);
        }
    }
}
```

## 函数

概念：一段具有特定功能的代码，可以重复使用

```java
class TestFunction{
	public static void main(String[] args){
        System.out.println("文能挂机骂队友");
		for(int i=1;i<=20;i++){
			System.out.print("-");
		}
		System.out.println();
        System.out.println("武能越塔送人头");
		for(int i=1;i<=20;i++){
			System.out.print("-");
		}
		System.out.println();
        System.out.println("进可孤身一挑五");
		for(int i=1;i<=20;i++){
			System.out.print("-");
		}
		System.out.println();
        System.out.println("退可坐等十五投");
		for(int i=1;i<=20;i++){
			System.out.print("-");
		}
		System.out.println();
    }
}
//代码存在问题：代码冗余  可维护性差
//解决办法：将打印分割性的功能代码写在一个函数中，当使用此功能时，直接调用函数
```

语法结构：

```java
public static void 函数名(){
    //业务代码（功能代码）
}
```

函数位置：类的内部，其他函数的外部

```java
//位置1
class Test{
    //位置2
    public static void main(String[] args){
       //位置3 
    }
    //位置4
}
//位置5

注意：位置2和位置4可以写函数，通常都在位置4写函数
```

调用语法：通过 `函数名()` 调用函数

注意：调用函数时，会优先执行函数内部代码，执行完毕后，返回到函数调用处，执行后续代码

### 函数参数

> 大多数情况，函数和函数的调用者是要有交互的；调用者必须提供某些数据，函数才能顺利执行下去；调用函数时所提供的数据就是函数的`参数`

定义语法：

```java
public static void 函数名(形式参数列表){
    //业务代码
}
//经验：形参 等价于声明了一个作用范围在整个函数内部的局部变量
//声明语法 ： 形参数据类型 形参名
```

调用语法：

```java
通过：函数名(实际参数)  调用函数
经验：实参  就是一个真正的、确切的数值，用来给形参赋值
注意：调用带参数的函数时，必须传入实参；实参的数据类型要和形参的数据类型一
```

### **单个参数**

```java
class TestFunction{
  public static void main(String[] args){
        System.out.println("文能挂机骂队友");
        //调用函数，函数名(实参)，传入实参 5
    printLine(5);
        System.out.println("武能越塔送人头");
    printLine(10);
        System.out.println("进可孤身一挑五");
    printLine(15);
        System.out.println("退可坐等十五投");
    printLine(20);
    }
  //声明函数，函数功能，打印count个"-"
  //形参：int count
  public static void printLine(int count){
    for(int i=1;i<=count;i++){
      System.out.print("-");
    }
    System.out.println();
  }
}
```

### 多个参数

```java
class TestFunction{
  public static void main(String[] args){
        System.out.println("文能挂机骂队友");
    //调用函数 函数名(实参1，实参2) 传入实参5，"="
    printLine(5,"=");
        System.out.println("武能越塔送人头");
    printLine(10,"+");
        System.out.println("进可孤身一挑五");
    printLine(15,"-");
        System.out.println("退可坐等十五投");
    printLine(20,"<>");
    }
  //声明函数，函数功能，打印count个sign
  //形参：int count，String sign
  public static void printLine(int count,String sign){
    for(int i=1;i<=count;i++){
      System.out.print(sign);
    }
    System.out.println();
  }
}
```

注意：当函数有多个参数时，调用函数时所传入的实参要和形参顺序、类型、个数保持一致

> 什么时候需要定义参数？
>
> 根据需求

总结：形参实际是告诉函数的调用者，想要函数顺利执行，需要提供什么类型的数据；实参就是函数的调用者提供的具体数据

### 返回值与返回值类型

> 一些情况下，函数执行结束后，是不需要返回结果的；某些情况下，则需要返回结果；
>
> 例如：存钱 是不需要返回结果；取钱 需要返回结果

定义语法：

```java
public static 返回值类型 函数名(形参列表){
    //业务代码
    return value;
}
//返回值类型，规定了函数要返回一个什么类型的结果
//（类型：基本类型，应用类型，void无返回值类型）
//return 表示返回，将return后面的value返回到函数调用处
//注意：返回值value的数据类型要和函数声明中写的返回值类型保持一致
```

调用语法：

```java
变量 = 函数名(实参列表)；
注意：
1.可以用一个变量来接受函数返回值；变量类型要和返回值类型保持一致
2.也可以选择不用变量接收
​
class Test{
  public static void main(String[] args){
    int c = add(5,6);
    //add(6,7);
    System.out.println(c);
    System.out.println(add(5,6));
    
  }
  public static int add(int a,int b){
    return a+b;
  }
}
```

* return的两种用法
  * 在有返回值类型的函数中，return后面跟返回值，表示结束函数，同时将返回值返回到函数调用处
  * 在无返回值类型\(void\)的函数中，同样可以使用return，return后面直接跟`分号;`，表示结束函数

```java
class Test{
	public static void main(String[] args){
		method();
    }
    public static void method(){
        for(int i=1;i<=10;i++){
            if(i==5){
                return;
            }
            System.out.println(i);
        }
    }
}
```

return使用要求

* 一个函数中只能有一个return语句,只能有一个返回值结果
* 当函数中存在分支结构，必须保证每个分支都有return语句（无论如何，一定要保证有返回值类型的函数，有return语句）

```java
class Test{
    public static void main(String[] args){
        
    }
    public static int method1(){
        int a = 10;
        int b = 20;
        return a;
        return b;//错误，函数中只能有一个return语句
    }
    public static String method2(int n){
        if(n%2==0){
            return "偶数"；
        }
        //错误，假如if条件为false，怎不执行if代码块
        //则函数缺少return语句
    }
    public static String method3(int n){
        if(n%2==0){
            return "偶数"；
        }else{
            return "奇数"；
        }
        //正确：if else 总会执行一个，函数有return语句
    }
    public static int method4(){
        for(int i=1;i<=10;i++){
            return i;
        }
        //错误，编译器，会从最坏的角度考虑代码的语法完整，会觉		得当for一次也不循环时，函数就缺少return语句
		return -1;
    }
}
```

### 随堂练习

```java
1.写一个函数，接受一个整数参数n，打印出n个HelloWorld
class Test1{
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		System.out.println("请输入一个整数：");
		int m = sc.nextInt();
		print(m);
	}
	public static void print(int n){
		for(int i=1;i<=n;i++){
			System.out.println("Hello World");
		}
	}
}
2.写一个函数add，从黑窗口接受两个整数作为参数，返回这两个整数的和。
class Test2{
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		System.out.println("请输入第一个整数：");
		int m = sc.nextInt();
		System.out.println("请输入第二个整数：");
		int n = sc.nextInt();
		int he = add(m,n);
		System.out.println("两个整数的和是"+he);
	}
	public static int add(int a,int b){
		//return a+b;
		int c = a+b;
		return c;
	}
}
3.写一个函数，从黑窗口接受一个整数n，返回1+2+3+…+n 的和
class Test3{
	public static void main(String[] args){
		System.out.println(add(100));
	}
	public static int add(int n){
		int sum = 0;
		for(int i = 1;i<=n;i++){
			sum +=i;
		}
		return sum;
	}
}


```

### 总结

1. 一个类中可以定义多个函数，函数之间属于并列关系，不可嵌套
2. 函数三要素：返回值类型，函数名，形参列表
3. 经验：一个函数，只做一件事情（一个功能）
4. 好处：
   * 解决代码冗余
   * 提高可维护性
   * 提高可复用性
   * 提高可读性

## 函数高级使用技巧

### **嵌套调用**

概念：在一个普通函数中调用其他函数

```java
class Test{
	public static void main(String[] args){
        m1(10);
    }
    public static void m1(int a){
        System.out.println("m1(a)-start");
        m2(a);
        System.out.println("m1(a)-end");  
    }
    public static void m2(int b){
        System.out.println("m2(b)-start");
        m3(b);
        System.out.println("m1(b)-end");  
    }
    public static void m3(int c){
        System.out.println("m3(c)-start");
        System.out.println(c);
        System.out.println("m3(c)-end"); 
    }
}


```

总结：

1. 当发生多重函数嵌套调用时，嵌套的最深层次的函数先执行结束，执行结束后，返回函数调用处执行后续代码；直到整个嵌套函数执行完毕
2. 调用者函数的形参可以作为被调用函数的实参

## **递归**

概念：在一个函数内部，调用自身（自己调自己）

作用；在实际开发中，可以帮助我们解决某些特定的问题

```java
class Test{
	public static void main(String[] args){
        m1();
    }
    public static void m1(){
        System.out.println("m1()-start");
        m1();
        System.out.println("m1()-end");  
    }
}
//设置一个有效的出口条件，避免无穷递归
```

* 什么时候使用递归？
  * 当需要解决的问题，可以拆分为若干小问题，并且大问题和小问题的解题方法相同
  * 有固定规律，函数中自己调自己
* 注意：所有能够使用递归解决的问题，循环都能解决

```java
//需求：定义一个函数，使用循环的方式计算整数n的阶乘，返回到函数调用处打印
class Test1{
	public static void main(String[] args){
        jieCheng(5);
    }
    public static int jieCheng(int n){
        int m = 1;
        for(int i=1;i<=n;i++){
            m*=i;
        }
        return m;
    }
}
//需求：定义一个函数，使用递归计算整数n的阶乘，返回函数调用出打印结果
class Test2{
	public static void main(String[] args){
        jieCheng(5);
    }
    //n!=n*(n-1)!-->(n-1)!=(n-1)*(n-2)!
    //5！=5*4！-->4!=4*3!-->3!=3*2!-->2!=2*1!-->1!=1*0!-->0!=1;
    //jieCheng(n)的作用是求n的阶乘
    //jieCheng(n-1)的作用是求n-1的阶乘
    public static int jieCheng(int n){
        if(n==0){
            return 1;
        }
        return n*jieCheng(n-1);
       
    }
//5*jieCheng(4)-->5*4*jieCheng(3)-->5*4*3*jieCheng(2)-->5*4*3*2*jieCheng(1)-->5*4*3*2*1*jieCheng(0)-->5*4*3*2*1*1
}


```

#### 随堂练习

```java
随堂练习：斐波那契数列的第一个值和第二个值都是1，从第三个数开始，每个数等于前两个数的和（1,1,2,3,5,8,13...），写一个函数，接受一个数表示数列序号，返回序列中对应序号的值
class Test1{
	public static void main(String[] args){
		System.out.println("请输入一个大于0的整数");
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		System.out.println(feiBo(n));
	}
	//feiBo(n)这个函数的作用:找到n序列号对应值
	//feiBo(n-1),feiBo(n-2)
	//feiBo(n) = feiBo(n-1)+feiBo(n-2)
	public static int feiBo(int n){
		if(n==1||n==2){
			return 1;
		}
		return feiBo(n-1)+feiBo(n-2);
	}
}
class Test2{
	public static void main(String[] args){
		
	}
	public static void feiBo(int n){
		int a = 1;
		int b = 1;
		int c = 1;
		for(int i=3;i<=n;i++){
			c = a+b;//c=2 c=3 
			a = b;  //a=1 a=2
			b = c;	//b=2 b=3
		}
		System.out.println(c);
	}
} 
```

## java方法

Java方法是语句的集合，它们在一起执行一个功能。

* 方法是解决一类问题的步骤的有序组合
* 方法包含于类或对象中
* 方法在程序中被创建，在其他地方被引用

一般情况下，定义一个方法包含以下语法：

修饰符 返回值类型 方法名\(参数类型 参数名\){ ... 方法体 ... return 返回值; }

方法包含一个方法头和一个方法体。下面是一个方法的所有部分：

> **修饰符：**修饰符，这是可选的，告诉编译器如何调用该方法。定义了该方法的访问类型。
>
> **返回值类型 ：**方法可能会返回值。returnValueType 是方法返回值的数据类型。有些方法执行所需的操作，但没有返回值。在这种情况下，returnValueType 是关键字**void**。
>
> **方法名：**是方法的实际名称。方法名和参数表共同构成方法签名。
>
> **参数类型：**参数像是一个占位符。当方法被调用时，传递值给参数。这个值被称为实参或变量。参数列表是指方法的参数类型、顺序和参数的个数。参数是可选的，方法可以不包含任何参数。
>
> **方法体：**方法体包含具体的语句，定义该方法的功能。

### 实例

下面的方法包含 2 个参数 num1 和 num2，它返回这两个参数的最大值。

```java
/** 返回两个整型变量数据的较大值 */
public static int max(int num1, int num2) {
   int result;
   if (num1 > num2)
      result = num1;
   else
      result = num2;
 
   return result; 
}
```

### 方法调用

Java 支持两种调用方法的方式，根据方法是否返回值来选择。

当程序调用一个方法时，程序的控制权交给了被调用的方法。当被调用方法的返回语句执行或者到达方法体闭括号时候交还控制权给程序。

当方法返回一个值的时候，方法调用通常被当做一个值。例如：

```java
public class TestMax {
   /** 主方法 */
   public static void main(String[] args) {
      int i = 5;
      int j = 2;
      int k = max(i, j);
      System.out.println( i + " 和 " + j + " 比较，最大值是：" + k);
   }
 
   /** 返回两个整数变量较大的值 */
   public static int max(int num1, int num2) {
      int result;
      if (num1 > num2)
         result = num1;
      else
         result = num2;
 
      return result; 
   }
}


输出：
  
5 和 2 比较，最大值是：5
```

## void 关键字

本节说明如何声明和调用一个 void 方法。

下面的例子声明了一个名为 printGrade 的方法，并且调用它来打印给定的分数。

```java
public class TestVoidMethod {
  public static void main(String[] args) {
    printGrade(78.5);
  }
 
  public static void printGrade(double score) {
    if (score >= 90.0) {
       System.out.println('A');
    }
    else if (score >= 80.0) {
       System.out.println('B');
    }
    else if (score >= 70.0) {
       System.out.println('C');
    }
    else if (score >= 60.0) {
       System.out.println('D');
    }
    else {
       System.out.println('F');
    }
  }
}


输出：
C
```

这里printGrade方法是一个void类型方法，它不返回值。

一个void方法的调用一定是一个语句。 所以，它被在main方法第三行以语句形式调用。就像任何以分号结束的语句一样。

### 通过值传递参数

调用一个方法时候需要提供参数，你必须按照参数列表指定的顺序提供。

例如，下面的方法连续n次打印一个消息：

```java
public static void nPrintln(String message, int n) {
  for (int i = 0; i < n; i++) {
    System.out.println(message);
  }
}

```

下面的例子演示按值传递的效果。

该程序创建一个方法，该方法用于交换两个变量。

```java
public class TestPassByValue {
  public static void main(String[] args) {
    int num1 = 1;
    int num2 = 2;
 
    System.out.println("交换前 num1 的值为：" +
                        num1 + " ，num2 的值为：" + num2);
 
    // 调用swap方法
    swap(num1, num2);
    System.out.println("交换后 num1 的值为：" +
                       num1 + " ，num2 的值为：" + num2);
  }
  /** 交换两个变量的方法 */
  public static void swap(int n1, int n2) {
    System.out.println("\t进入 swap 方法");
    System.out.println("\t\t交换前 n1 的值为：" + n1
                         + "，n2 的值：" + n2);
    // 交换 n1 与 n2的值
    int temp = n1;
    n1 = n2;
    n2 = temp;
 
    System.out.println("\t\t交换后 n1 的值为 " + n1
                         + "，n2 的值：" + n2);
  }
}

以上运行如下：
  
交换前 num1 的值为：1 ，num2 的值为：2
    进入 swap 方法
        交换前 n1 的值为：1，n2 的值：2
        交换后 n1 的值为 2，n2 的值：1
交换后 num1 的值为：1 ，num2 的值为：2
```

## 方法重载

上面使用的max方法仅仅适用于int型数据。但如果你想得到两个浮点类型数据的最大值呢？

解决方法是创建另一个有相同名字但参数不同的方法，如下面代码所示：

```java
public static double max(double num1, double num2) {
  if (num1 > num2)
    return num1;
  else
    return num2;
}
```

如果你调用max方法时传递的是int型参数，则 int型参数的max方法就会被调用；

如果传递的是double型参数，则double类型的max方法体会被调用，这叫做方法重载；

就是说一个类的两个方法拥有相同的名字，但是有不同的参数列表。

Java编译器根据方法签名判断哪个方法应该被调用。

方法重载可以让程序更清晰易读。执行密切相关任务的方法应该使用相同的名字。

重载的方法必须拥有不同的参数列表。你不能仅仅依据修饰符或者返回类型的不同来重载方法

### 变量作用域

变量的范围是程序中该变量可以被引用的部分。

方法内定义的变量被称为局部变量。

局部变量的作用范围从声明开始，直到包含它的块结束。

局部变量必须声明才可以使用。

方法的参数范围涵盖整个方法。参数实际上是一个局部变量。

for循环的初始化部分声明的变量，其作用范围在整个循环。

你可以在一个方法里，不同的非嵌套块中多次声明一个具有相同的名称局部变量，但你不能在嵌套块内两次声明局部变量。

## 构造方法

当一个对象被创建时候，构造方法用来初始化该对象。构造方法和它所在类的名字相同，但构造方法没有返回值。

通常会使用构造方法给一个类的实例变量赋初值，或者执行其它必要的步骤来创建一个完整的对象。

不管你是否自定义构造方法，所有的类都有构造方法，因为Java自动提供了一个默认构造方法，默认构造方法的访问修改符和类的访问修改符相同\(类为 public，构造函数也为 public；类改为 private，构造函数也改为 private\)。

一旦你定义了自己的构造方法，默认构造方法就会失效。

```java
// 一个简单的构造函数
class MyClass {
  int x;
 
  // 以下是构造函数
  MyClass() {
    x = 10;
  }
}
```

```java
public class ConsDemo {
   public static void main(String args[]) {
      MyClass t1 = new MyClass();
      MyClass t2 = new MyClass();
      System.out.println(t1.x + " " + t2.x);
   }
}
```

示例：

```java
// 一个简单的构造函数
class MyClass {
  int x;
 
  // 以下是构造函数
  MyClass(int i ) {
    x = i;
  }
}
```

```java
public class ConsDemo {
  public static void main(String args[]) {
    MyClass t1 = new MyClass( 10 );
    MyClass t2 = new MyClass( 20 );
    System.out.println(t1.x + " " + t2.x);
  }
}
```

### 可变参数

JDK 1.5 开始，Java支持传递同类型的可变参数给一个方法。

方法的可变参数的声明如下所示：

typeName... parameterName

在方法声明中，在指定参数类型后加一个省略号\(...\) 。

一个方法中只能指定一个可变参数，它必须是方法的最后一个参数。任何普通的参数必须在它之前声明。

```java
public class VarargsDemo {
    public static void main(String args[]) {
        // 调用可变参数的方法
        printMax(34, 3, 3, 2, 56.5);
        printMax(new double[]{1, 2, 3});
    }
 
    public static void printMax( double... numbers) {
        if (numbers.length == 0) {
            System.out.println("No argument passed");
            return;
        }
 
        double result = numbers[0];
 
        for (int i = 1; i <  numbers.length; i++){
            if (numbers[i] >  result) {
                result = numbers[i];
            }
        }
        System.out.println("The max value is " + result);
    }
}


运行结果：
The max value is 56.5
The max value is 3.0
```



