# Day1

### java环境配置

JDK=JRE+编译器+类库

JRE : java运行环境 JRE=虚拟机（JVM）+解释器

JVM: 屏蔽底层操作系统的差异 ，使所有java程序可直接运行在JVM中

过程：java代码----JVM----操作系统

## 第一个Java代码

1.新建一个java源文件（.java）

2.class类，java程序基本组成单元，是盛放代码的容器。一个源文件可以有多个类。通过类名区分不同的类。

* 主函数 ，或入口函数，程序的入口

```java
public static void main(String[] args){

}
```

* 输出语句，输出到控制台

```java
System.out.println("Hello World");
```

* 编译命令：javac 源文件名.java
* 运行命令：java 类名
* public class : 表示公众类
  * 公开类的类名必须与源文件名保持一致
  * 一个源文件中可以不写公开类，写了最多只能写一个公开类



