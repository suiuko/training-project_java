# Day2

## 编码规范

### 1.标识符命名规范

标识符：类名，变量名，方法等

**规定：**

1. 只能由字母，数字，下划线，$组成
2. 数字不能开头
3. 大小写敏感
4. 不能和关键字和保留字名字重复

**规范：**

1. 类名命名时，可以由多个单词，没个单词首字母大写
2. 函数名和变量名命名时，也可以有多个单词，首单词首字母小写，后面的单词首字母大写
3. 包名全小写
4. 常量名全大写，每个单词之间由下划线连接

### 代码书写规则

1. 层级之间需要缩进
2. 一行只有一句代码

### 注释

注释写在代码之间，

1. 单行注释    //这里是单行注释
2. 多行注释   /\*  这里是多行注释\*/
3. 文档注释 / **\*\* 这里是文档注释 \*\*** /

## 变量与数据类型

### 变量

概念：计算机内存中的一块空间，用来保存数据

> 一个酒店是内存的话，酒店中有很多许多房间
>
> * 房间类型（单人，双人）
> * 门牌号（唯一的门牌号）
> * 住客
>
> 酒店--------内存
>
> 房间--------变量
>
> 房间类型------数据类型
>
> 门牌号 ------变量名
>
> 住客-----变量中保存的数据数值

### 声明变量：

数据类型  变量名    p.s:   int a;

**JAVA是一个强类型语言，每一个变量中的数据类型要和声明变量时的类型一致**

变量初始化：所谓给变量赋值， 变量名=值； P.S. a=10;

或者声明的同时给变量赋值 P.S. int a = 10 ;

#### 数据类型

java中，数据分为基本数据类型（简单数据类型）和引用数据类型（对象类型）

**基本数据类型（8小种）：**

包含整形 ， 浮点型，字符型，布尔型

**引用数据类型（无穷多）：**

String（字符串），数组，对象等

**基本数据类型--整形**

| 类型 | 字节 | 取值范围 |
| :--- | :--- | :--- |
| byte | 1B | -2^7~2^7-1 |
| short | 2B | -2^15~2^15 |
| int | 4B | -2^31~2^31 |
| long | 8B | \`2^63~2^63 |

```java
class Test{
    public static void main(String[] args){
    byte b = 10;
    short s = 10;
    int i = 30;
    //Java默认整形为int
    long l = 40L;
```

### 基本数据类型 -- 浮点（小数）

| 类型 | 字节 |
| :--- | :--- |
| float（单精度） | 4B |
| double（双精度） | 8B |

Java默认是使用double

### 基本数据类型 -- 字符（char）

| 类型 | 字节 | 取值 |
| :--- | :--- | :--- |
| char | 2B | 0~65535 |

1. 用''括起来
2. 用数字表示
3. 用unicode表示

```java
char c1 = 'A';char c2 = '中';
char c3 = 65;
char c4 = '\u0041';
```

### 基本数据类型 -- 布尔（boolean）

数值只有两个，True和False

```java
boolean b1 = true;
boolean b2 = 5>4
```

### 引用类型（对象类型）

String 字符串，用"" 括起来的一个或多个字符。

> 补充：字符串可以通过“+“来拼接，任何数字类型通过“+“号连接字符串，输出结果都为字符串

```java
class test{
    public static void main(String [] args){
        int a = 10;
        int b = 9;
        System.out.println(a+","+b);
}
```

### 数据类型转换与自动类型提升

#### 自动数据转换

小数据类型变量可以直接转换为大数据类型变量

> byte - &gt;short -&gt; int -&gt;long -&gt;float -&gt;double
>
> char -&gt;int   char只能给int

```java
class test{
    public static void main(string[] args){
    byte b = 10;
    short s = b;
    int i = s;
    long l = i;
    float f = l;
    double d= f;
    System.out.println(b+","+s+","+i+","+l+","+f+","+d);
    }
}
```

#### 强制类型转换

将大数据类型变量强行转变为小数据类型变量（可能发生精度丢失）

语法

> 小数据类型 = （小数据类型） 大数据类型

```java
int i = 10;
byte b = (byte) i; 
```

规则：

> 1.大数据类型变量的值在小数类型的取值范围之内，数据完整。
>
> > int i =100; 
> >
> > byte b = \(byte\) i;//b=100
>
> 2.大数据类型变量的值在小数据类型变量的值之外，舍去高位字节。
>
> > int i = 10000;
> >
> >  byte b =\(byte\) i;//int 4个字节，byte1个字节，则舍去高位三个字节，即b=16
> >
> > 还可能发生符号位变化，如正变负
>
> 3.小数强转为整数，直接舍去小数部分，没有四舍五入
>
> > double d = 12.9; 
> >
> > int i = \(double\)d;//i=12

#### 自动类型提升

当多个数据进行算数运算时

1. 若其中有Double类型数据，那么运算结果为Double类型
2. 若其中有Float类型数据，那么运算结果为Float类型
3. 托其中有long类型数据，则运算结果为long类型
4. 其他情况默认提升为int类型

### 表达式与运算符

#### 表达式

通过运算符将变量或者值连接到一起，并且一定会有一个最终结果

```java
1+2;
int a=10; a-5;
int a=10; int b=20; a*b; b/a; a>50; a<50;
```

#### 运算符

| 操作符 | 描述 |
| :--- | :--- |
| + | 加，求和 |
| - | 减，求差 |
| \* | 乘，求积 |
| / | 除，求商 |
| % | 模，求余 |

```java
int c=5;
c++;//c自增之前的值，c为5
++c;//c自增之后的值，c为7
```

#### 赋值运算符

| 运算符 | 描述 |
| :--- | :--- |
| = | 将右边赋值给左边 |
| += | 求和后赋值 |
| -= | 求差后赋值 |
| \*= | 求积后赋值 |
| /= | 求商后赋值 |
| %= | 求模后赋值 |

```java
int a=10;
a+=3;//等价于 a=a+3;
//这种运算符不会发生自动类型提升
int b=20;
b-=5;//等价于 b=b-5;
```

#### 关系运算符

| 运算符 | 描述 |
| :--- | :--- |
| &gt;= | 大于等于 |
| &lt;= | 小于等于 |
| == | 判断是否相等 |
| != | 不等于 |
| &gt; | 大于 |
| &lt; | 小于 |

得到布尔运算结果

#### 逻辑运算符

| 运算符 | 描述 |
| :--- | :--- |
| && | 判断两边数据或表达式是否同时为真，总结果为真 |
| \|\| | 判断两边数据或表达式是否有一方为真，总结果为真 |
| ！ | 取反，！True==False,反之亦然 |
| \| | 不短路或 |
| & | 不短路与 |

```java
a||b //如果a真，那就不用继续计算
a|b //如果a真，还继续运算
a&&b //如果a为假，不用继续计算
a&b // 如果a为假，继续计算
```

#### 三元运算符

| 符号 | 形式 | 说明 |
| :--- | :--- | :--- |
| ？： | a?b:c | 如果a为True，则执行b,否则执行c |

## 选择结构与分支

### 选择结构

根据已知条件进行判断，满足条件执行相应的操作

### if 基本选择

语法：

```java
if（布尔表达式）
{
    //业务代码
}
//后续代码
```

执行流程：

1. 先对布尔表达式进行判断
2. 结果为true则执行业务代码，之后执行后续代码
3. 结果为false，跳过业务代码，直接执行后续代码

```java
int a=5;
if(a%2==0)
{
 	System.out.println("a为偶数");   
}
System.out.println("a的值为"+a); 
```

### if else 选择结构

语法：

```java
if(布尔表达式)
{
    //代码1 如果布尔表达式的值为true
}
else
{
    //代码2 如果布尔表达式的值为false
}
```

* 对布尔表达式判断，
* 如布尔表达式为true，则运行代码1，之后执行后续代码。
* 如为false则运行代码2，之后执行后续代码。

```java
int a=5;
if(a%2==0)
{
 	System.out.println("a为偶数");   
}
else
{
	System.out.println("a是奇数");  
}
System.out.println("a的值为"+a);   
```

### 多重 if else if 选择结构

语法：

```java
if(布尔表达式1)
{
    //代码1
}
else if(布尔表达式2)
{
    //代码2
}
else if(布尔表达式3)
{
    //代码3
}
else
{
    //代码4
}
```

* 对布尔表达式1判断，如结果为true，运行代码1，跳出选择结构；如为false，对布尔表达式2判断
* 布尔表达式2为true，执行代码2，跳出选择结构；为false，对布尔表达式3判断
* 布尔表达式3为true，执行代码3，跳出选择结构；为false，执行else内代码4
* 执行完代码4，跳出选择结构

### 嵌套if选择结构

语法：

```java
if(外层表达式)
//如果布尔表达式 1的值为true执行代码
{
    if（内层表达式）
    {
    //内层业务代码1
    //如果布尔表达式 2的值为true执行代码    
    }
    else   
    {
        //内层业务代码2
    }
}
else
{
    //外层业务代码
}
```

* 先判断外层表达式，如果结果为true，对内层表达式进行判断，如果内层表达式为true，执行内层业务代码1.

  _**注意：只要满足语法结构，可以任意嵌套**_

```java
public class Test {
    public static void main(String args[]){ 
        int x = 30; 
        int y = 10; 
        if( x == 30 ){     
            if( y == 10 ){         
                System.out.print("X = 30 and Y = 10");      
            }   
        }
    }
}//分支结构
```

语法：

```java
switch(变量或表达式)
{
    case 值1:
        //业务代码1
        break;//跳出分支结构
    case 值2：
        //业务代码2
        break;
    case 值n：
        //业务代码n
        break;
    default:
        //若所有case值都不匹配，执行最终默认执行代码
}
```

* 判断条件变量或表达式类型：byte，short，int，char，String（jdk7以上版本）
* break表示跳出结构

执行流程：

1. 对变量或表达式进行匹配
2. 若与case值1相等，则执行业务代码1，随后break跳出结构
3. 若与case值2相等，则执行业务代码2，随后break跳出结构
4. 若与case值n相等，则执行业务代码n，随后break跳出结构
5. 若与所有case值都不匹配则，执行default默认代码

## Switch case 语句

#### 语法

switch case 语句语法格式如下：

```java
switch(expression){
    case value :
       //语句
       break; //可选
    case value :
       //语句
       break; //可选
    //你可以有任意数量的case语句
    default : //可选
       //语句
}
```

switch case 语句有如下规则：

* switch 语句中的变量类型可以是： byte、short、int 或者 char。从 Java SE 7 开始，switch 支持字符串 String 类型了，同时 case 标签必须为字符串常量或字面量。
* switch 语句可以拥有多个 case 语句。每个 case 后面跟一个要比较的值和冒号。
* case 语句中的值的数据类型必须与变量的数据类型相同，而且只能是常量或者字面常量。
* 当变量的值与 case 语句的值相等时，那么 case 语句之后的语句开始执行，直到 break 语句出现才会跳出 switch 语句。
* 当遇到 break 语句时，switch 语句终止。程序跳转到 switch 语句后面的语句执行。case 语句不必须要包含 break 语句。如果没有 break 语句出现，程序会继续执行下一条 case 语句，直到出现 break 语句。
* switch 语句可以包含一个 default 分支，该分支一般是 switch 语句的最后一个分支（可以在任何位置，但建议在最后一个）。default 在没有 case 语句的值和变量值相等的时候执行。default 分支不需要 break 语句。

## 循环结构

满足判断条件，使某段的代码重复运行

### while 循环

语法：

```java
条件初始化
while(循环条件)
{
    //循环体，逻辑代码
}
```

执行流程：

1. 对循环条件进行判断
2. 结果为true，则执行循环体，然后再次执行判断
3. 直到判断结果为false，结束循环，执行后续代码

```java
//打印10次Hello World
int i = 1;//循环条件
while(i<=10)//判断条件
{
    System.out.println("Hello world");//循环体（逻辑代码）
    i++;//条件更新语句
}
```

循环以上面四个部分组成

```java
class TestWhile
{
    public static void main(String[] args)
    {
        int a=1;
        int b=1;
        int c=1;
        while(c<=10)
        {
            System.out.println("Hello World");
            a++;
            b++;
            c++;//谁参与循环谁才是循环变量
        }
    }
}
```

```java
//从1加到100的和
class Addto100
{
    public static void main(String[] args)
    {
        int a=0;
        int count=0;
        while(a<=100)
        {
            count+=a;
            a++;
        }
        System.out.println("1加到100等于："+count);
    }
}
```

```java
//从1加到100的奇数和
class Addto100byjishu
{
    public static void main(String[] args)
    {
        int a=0;
        int count=0;
        while(a<=100)
        {
            count+=a;
            a+=2;
        }
        System.out.println("1加到100的奇数和等于："+count);
    }
}
```

### 死循环

当布尔表达式为true是时候， 程序会一直执行

```java
class DeadWhile
{
    public static void main(String[] args)
    {//循环条件一直为true，死循环
        while(true)
        {
            System.out.println("Hello World");
        }
    }
}
class DeadWhile1
{
    public static void main(String[] args)
    {//缺少循环语句，循环变量永远不会发生变化
        //只要第一次判断为true，后面一直为true
        int i=5;
        while(i>=10)
        {
            System.out.println("Hello World");
        }
    }
}
```

关黑窗口：ctrl + c

```java
//猜大小
import java.util.Scanner;
import java.util.Random;
class Caidaxiao
{
    public static void main(String[] args)
    {
        Scanner sc=new Scanner(System.in);
        Random r= new Random();
        int m=r.nextInt(101);//获取随机数（0~100）
        System.out.println("欢迎来到猜大小，猜一个数：");
        while(true)
        {
            int n =sc.nextInt();
            if(n==m)
            {
                System.out.println("猜对了！");
                //跳出循环
                break;
            }else if(n<m)
            {
                System.out.println("猜小了！再猜一个数：");
            }else 
            {
                System.out.println("猜大了！再猜一个数：");
            }
        }
    }
}
```

while : 先判断，再循环

### do while 

对于 while 语句而言，如果不满足条件，则不能进入循环。但有时候我们需要即使不满足条件，也至少执行一次。

do…while 循环和 while 循环相似，不同的是，do…while 循环至少会执行一次。

语法

```java
do
{
    //循环体代码
}
while(循环条件布尔表达式)；
```

执行流程：

1. 先执行一次循环体
2. 在判断一次循环条件，满足条件就循环，不满足就跳出

特点：

先执行，后判断

**注意：**布尔表达式在循环体的后面，所以语句块在检测布尔表达式之前已经执行了。 如果布尔表达式的值为 true，则语句块一直执行，直到布尔表达式的值为 false。

### Break 关键字

break 主要用在循环语句或者 switch 语句中，用来跳出整个语句块。

break 跳出最里层的循环，并且继续执行该循环下面的语句。

```java
break;
```

```java
public class Test {
   public static void main(String args[]) {
      int [] numbers = {10, 20, 30, 40, 50};
 
      for(int x : numbers ) {
         // x 等于 30 时跳出循环
         if( x == 30 ) {
            break;
         }
         System.out.print( x );
         System.out.print("\n");
      }
   }
}
```

### for 循环

语法：

```java
for(循环变量（1）;循环条件（2）;循环更新语句（更新4）)
{
    //循环体（3）
}
```

执行流程：

1. 先初始化循环变量，此操作只执行一次
2. 进行循环条件判断，满足条件，执行循环体
3. 然后，执行条件更新语句，在进行循环条件判断
4. 满足条件，执行循环体，直到不满足条件，结束循环

执行顺序：（1）（2）（3）（4）--&gt;（2）（3）（4）--&gt;（2）（3）（4）....（2）不满足为止

（1） 负责完成循环变量初始化

（2）负责判断是够满足循环条件，不满足则跳出循环

（3）具体执行的语句

（4）循环后，循环条件所涉及变量的变化情况

关于 for 循环有以下几点说明：

* 最先执行初始化步骤。可以声明一种类型，但可初始化一个或多个循环控制变量，也可以是空语句。
* 然后，检测布尔表达式的值。如果为 true，循环体被执行。如果为false，循环终止，开始执行循环体后面的语句。
* 执行一次循环后，更新循环控制变量。
* 再次检测布尔表达式。循环执行上面的过程。

特点：

先判断，再执行

```java
//需求：打印10边Helloworld
class TestFor
{
    public static void main(String[] args)
    {
        for(int i=1;i<=10;i++)
        {
            System.out.println("Hello World");
        }
    }
}
```

循环更新语句可省，但会死循环。判断条件可省，但会失去判断能力。

### 总结：while循环为不确定循环，for循环为确定循环

```java
//随堂作业：从黑窗口获取一个整数n，打印这个整数n为几位数
import java.util.Scanner;
class Youjiwei
{
    public static void main(String[] args)
    {
		System.out.println("输入一个数：");
        Scanner sc=new Scanner(System.in);
		int n =sc.nextInt();
		int w=0;
		do
		{
			n=n/10;
			w++;
		}while(n!=0);
		System.out.println("有"+w+"位");
    }
}
```

## 嵌套循环

所谓的嵌套循环，是指一个循环的循环体是另一个循环，for循环中为：

总共的循环次数 = 外循环次数 \* 内循环次数

```java
for(初始化表达式(1);循环条件(2);步进表达式(2)){
  for初始化表达式(3);循环条件(4);步进表达式(6){
    执行语句(5);
  }
}
```

嵌套循环执行流程：

执行顺序：\(1\)\(2\)\(3\)\(4\)\(5\)\(6\) ---&gt;\(4\)\(5\)\(6\) ---&gt;\(7\)\(2\)\(3\)\(4\)\(5\)\(6\) ---&gt;\(4\)\(5\)\(6\)

外循环一次，内循环多次。

**题目：输出1-100 第五个偶数**

```java
public class text2 {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		//输出1-100之间的第五个偶数
		int b=0;
		for(int i=1;i<100;i++) {
			if(i%2==0) {
				
				b++;
				if(b!=5) {
					continue;
				}
				System.out.println("第五个偶数是："+i);
			}
		}
	}


```

