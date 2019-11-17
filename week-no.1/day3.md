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

