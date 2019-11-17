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



