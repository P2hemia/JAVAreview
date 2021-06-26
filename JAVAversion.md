# JAVA基础知识点总结
---
本文主要从Java基础的知识点入手，将一些个人总结的方法以及部分源码会以文件的形式放在GitHub上面以供大家参考，若有问题，还请纠正。
>Java语言发展历史

1990 年末，Sun 公司准备为下一代智能家电（电视机，微波炉，电话）编写一个通用的控制系统。该团队最初考虑使用 C++语言，很多成员包括 Sun 公司的首席科学家 Bill Joy，发现C++语言在某些方面复杂，系统资源极其有限，缺少垃圾回收系统等，于是 Bill Joy 决定开发一种新的语言：Oak。

1992 年夏天，Green 计划已经完成新平台的部分功能，包括 Green 操作系统，Oak 的程序设计语言、类库等。同年 11 月，Green 计划被转成“FirstPerson 有限公司”，一个 Sun 公司的全资子公司。该团队致力于创建一种高度互动的设备。

1994 年夏天，互联网和浏览器的出现不仅给广大互联网的用户带来了福音，也给 Oak 语言带来了新的生机。James Gosling（Java 之父）立即意识到，这是一个机会，于是对 Oak 进行了小规模的改造。

1994 年秋，小组中的 Naughton 和 Jonathan payne 完成了第一个 Java 语言的网页浏览器：WebRunner。Sun 公司实验室主任 Bert Sutherland 和技术总监 Eric Schmidt 观看了该网页的演示并给予了高度的评价。当时 Oak 这个商标已经被注册了，于是将 Oak 改名为 Java。

1995 年初，Sun 公司发布 Java 语言，Sun 公司直接把 Java 放到互联网上，免费给大家使用，甚至连源代码也不保密，也放在互联网公开。几个月后，Java 成了互联网上最热门的宝贝。各种各样的小程序层出不穷，Java 终于扬眉吐气，成为了一种广为人知的编程语言。

1996 年底，Flash 问世了，这是一种更加简单的动画设计软件：使用 Flash 几乎无须任何编程语言知识，就可以做出丰富多彩的动画。Flash 逐渐蚕食了 Java 在网页上的应用。

1997 年 2 月 18 日，Sun 公司发布了 JDK1.1，增加了即时编译器 JIT。

1995 年 Java 诞生到 1998 年底，Java 语言虽然成为了互联网上广泛使用的编程语言，但它没有找到一个准确的定位。

1998 年 12 月，Sun 发布了 Java 历史上最重要的 JDK 版本：JDK1.2。并将 Java 分成了 J2EE（提供了企业应用开发相关的完整解决方案）、J2SE（整个 Java 技术的核心和基础）、J2ME（主要用于控制移动设备和信息家电等有限存储的设备）三个版本。

2002 年 2 月，Sun 发布了 JDK 历史上最为成熟的版本，JDK1.4。

2004 年 10 月，Sun 发布了万众期待的 JDK1.5，JDK1.5 增加了诸如泛型、增强的 for 语句、可变数量的形参、注释、自动拆箱和装箱等。

2005 年，Java 诞生十周年，J2SE/J2EE/J2ME 分别改名为：JavaSE/JavaEE/JavaME。

2006 年 12 月，Sun 发布了 JDK1.6。

2009 年 4 月 20 日，Oracle 甲骨文公司宣布将以每股 9.5 美元的价格收购 Sun。Oracle 通过收购 Sun 获得了两项资产：Java 和 Solaris。

2007 年 11 月，Google 宣布推出一款基于 Linux 平台的开源手机操作系统：Android。Android使用 Java 语言来开发应用程序。Android 平台的流行，让Java 语言获得了在客户端程序上大展拳脚的机会。

2011 年 7 月 28 日，Oracle 发布了 Java SE7，这次版本升级耗时将近 5 年时间。引入二进制整数、支持字符串的 switch 语句等。

2014 年 3 月 18 日，Oracle 发布了 Java SE 8。

2017 年 7 月，Oracle 发布了 JavaSE 9。

2018 年 3 月 20 日，Oracle 发布了正式版 JavaSE 10。同一年 9 月 25 日发布了 Java11。

2019 年 3 月 19 日，Oracle 发布了 Java12。

以上的描述就是 Java 一路走来的发展历程，我们只能说：Java，你好坚挺啊！在这个发展的过程中一代语言的兴起又衰败，又兴起又衰败，但Java 这 24 年来一直立于不败之地。并且渗透到每个行业，已然根深蒂固。
## 1 Java基础
---
>考虑到有些同学还不会安装Java编译器或者不懂基本操作的同学，在这里就不多加演示如何安装和一些基本操作了，这里就直接总结知识点了。

### 1.1 Java中的注释
---
Java语言的注释包括三种方式，它们分别是：
* 1 单行注释，语法格式如下：
> //  单行注释，两个正斜杠后面的内容被注释

* 2 多行注释，语法格式如下：
> /* 
> *这里的信息为多行注释：
> *第一行注释信息
> *第二行注释信息
> */

* 3 Javadoc注释，语法格式如下：
> /**
> *这里的信息是Javadoc注释：
> *@author 作者名字
> *@version 版本号
> *@since 自从哪个版本号开始就存在了
> *@email 作者邮箱
> */
### 1.2 public class 和 class 的区别
---
每个编译单元（文件）都只能有一个public类。即每个编译单元都有单一的公共接口，用public类实现。此时，mian()就必须要包含在public类中。
public类的名称必须完全与含有该编译单元的文件名称一致，包括大小写。如果不匹配，编译时错误。
如果编译单元（文件）中不含有一个public类，此时编译单元文件名称可以与启动类名称可以不一致，即可以随意对文件命名。这样的话，main()不是必须要放在public类中才能运行程序。
总的来说，一个Java源文件中最多只能有一个public类，当有一个public类时，源文件名必须与之一致，否则无法编译，如果源文件中没有一个public类，则文件名与类中没有一致性要求。至于main()不是必须要放在public类中才能运行程序。
### 1.3 标识符与关键字
标识符是指用来标识某个实体的符号，在不同的应用环境下有不同的含义。在计算机编程语言中，标识符是用户编程时使用的名字，用于给变量、常量、函数、语句块等命名，以建立起名称与使用之间的关系。标识符通常由字母和数字以及其他字符构成。
在编程语言中，标识符就是程序员自己规定的代表一定含义的单词，比如类名、属性名、变量名等。
#### 1.3.1 标识符命名规则
标识符主要用来起名字，那么可以随便起名吗，有没有什么命名规则呢，答案是：有的，
而且还得必须遵守，当编写源程序的时候如果标识符违背命名规则，编译时会报错。那么 java中的标识符命名规则有哪些呢？请看以下规则：
① 标识符只能由数字、字母、下划线“_”、美元符号“$”组成，不能含有其它符号。
② 标识符不能以数字开始。
③ java 关键字和保留字不能作为标识符。
④ 标识符严格区分大小写。
⑤ 标识符理论上没有长度限制。
以上几点需要大家在以后不断的练习中进行掌握，不需要死记硬背
#### 1.3.2 标识符命名规范
① 见名知意：看到这个单词就知道它表示什么，增强程序的可读性，例如：Student 则表
示学生类型，User 则表示用户类型；
② 遵循驼峰命名方式：可以很好的分隔单词，每个单词之间会划清界限，同样也是增强程序的可读性，例如：getName 则表示获取名字，UserService 则表示用户业务类；
③ 类名、接口名首字母大写，后面每个单词首字母大写，这是遵守驼峰命名方式的；
④ 变量名、方法名首字母小写，后面每个单词首字母大写，这也是遵守驼峰命名方式的；
⑤ 常量名全部大写，单词和单词之间使用“_”衔接，为了表示清楚含义，不要怕单词
长，例如：INT_MAX_VALUE 则表示 int 类型最大值。
### 1.4 数据类型
>Java中最常见的共有八种基本数据类型：

| 数据类型 |占字节数|
|:-------:|:------:|
|byte（字节型）| 1 |
|short（短整型）| 2|
|int（整型） |4 |
|long（长整型） |8 |
|float（单精度） |4 |
|double（双精度） |8 |
|boolean（布尔型）| 1 |
|char（字符型） | 2 |
### 1.5 运算符
#### 1.5.1 逻辑运算符
> 逻辑运算符的特点是操作数都是布尔类型，并且最终结果也都是布尔类型。

|操作符| 例子| 结果 |描述|
|------|----|------|----|
|&| true&true |TRUE| (5>3) & (5>4)：5 大于 3 并且 5 大于 4，有道理|
|  \| |true\|false| TRUE | (5>3)  (5>10)：5 大于 3 或者 5 大于 10，没毛病|
|!| !false| TRUE |false 取反是 true，true 取反就是 false|
|^| true^false |TRUE|异或运算符,只要两边的操作数不同，结果就是true|
|&& |true&&true| TRUE|短路与（&&）和逻辑与（&）实际上最终的运行结果是完全相同的，只不过短路与（&&）会存在短路现象|
|\|\|| true\|\|false| TRUE|短路或（\|\|）和逻辑或（\|）实际上最终的运行结果是完全相同的，只不过短路或（\|\|）会存在短路现象|
### 1.6 控制语句
控制语句主要有选择语句、循环语句、转向语句、返回语句，每种语句的具体用法如下：


#### 1.6.1 选择语句 if 语句和if else 语句

* if 语句格式：

```java
if (布尔表达式) {
一条或多条语句
}
```
如果语句为一条，可以省略大括号，如：
```java
 if(布尔表示式)
 一条语句
```
 只有表示为 true 时，才会进入 if 语句中
* if else 语句格式
```java
if (布尔表示式) {
一条或多条语句
}else {
一条或多条语句
}
```
如果 else 时，还需要条件，可以写成如下可是：
```java
if (布尔表示式) {
一条或多条语句
}else if(布尔表示式) {
一条或多条语句
} else {
一条或多条语句
}
```


#### 1.6.2 选择语句 switch语句
* switch 也称为多重分支，具体格式如下：
```java
switch (表达式) {
    case 值 1：
        语句 
        break;
    case 值 2：
        语句 
        break;
    default：
        语句
}
```
说明：
* 表达式的值只能为：char、byte、short、int 类型，boolean、long、float、double 都是非法的。
*  break 语句可以省略,但会出现 switch 穿透
* default 语句也可以省略，一般不建议省略
* **注意类的命名：首字母要大写，单词之间首字母大写，这种命名方式称为“驼峰标识”**


#### 1.6.3 循环语句 for语句
>for 语句格式如下：
```java
for(初始化部分表达式；条件表达式； 更新表达式) {
    一条或多条语句
}
```


#### 1.6.4 循环语句 while语句
>while 语句
```java
while(布尔表达式) {
    一条或多条语句
}
```
* 采用 for 语句完全可以模仿 while 语句，如将 for 语句中的“初始化部分表达式”和“更新表达式”省略
```java
for (; 条件表达式 ; ) {
    语句
}
```


#### 1.6.5 循环语句 do while 语句
>do while 语句格式
```java
do {
    语句
}while(布尔表达式);
```
**注意 while 括号后必须写分号do while 与 while 非常相似，不同点在于 do while 先执行循环体，也就是说不管条件符不符合，循环体至少执行一次**


#### 1.6.6 转向语句 break语句
---
break 可以用在 switch、循环语句和带标号的语句块中：
>**在循环语句中主要是为了终止**

>**在循环语句中主要是为了终止循环（多重循环）**


#### 1.6.7 转向语句 continue语句
---
**continue 只能用在循环语句中，表示在循环中执行到 continue 时，自动结束本次循环，然后判断条件，决定是否进行下一次循环（多个循环的跳出使用---标签：的方式）**



### 1.7 方法
---
>方法主要学习了解方法的定义，明白学会使用方法的调用，方法的重载和递归的算法
```java
[方法修饰列表] 返回值类型 方法名（方法参数列表）{
    方法
}
```
#### 1.7.1 方法的调用
---
>举例**存在返回值**
```java
public class MethodTest01 {
    public static void main(String[] args) {
    String s = method1(1);
    System.out.println(s);
    }
    public static String method1(int c) {
        String retValue= ""; 
        switch(c) {
          case 1: 
               //System.out.println("优秀");
                retValue = "优";
                break;
            case 2:
                //System.out.println("良好");
                retValue = "良好";
                break;
            case 3:
                //System.out.println("一般");
                retValue = "一般";
                break;
            default:
                //System.out.println("很差");
                retValue = "很差";
        }
        return retValue;
    }
}
```
* 通过以上程序我们可以看出，其实方法也没什么神秘的，方法其实就是一段普通的代码片段，并且这段代码可以完成某个特定的功能，而且可以被重复的调用/使用。java 中的方法又叫做 method，在 C 语言中叫做函数。
* 从现在开始大家以后在写代码的时候就要有定义方法的意了，只要是可以独立出来的功能，我们都可以定义为单独的一个方法来完成，如果以后需要使用此功能时直接调用这个方法就行了，不要把所有的代码都扔到 main 方法当中，这样会导致程序的“复用性”很差。
>接下来我将列出方法的相关规则，其中一些规则目前可能需要大家死记硬背，还有一些规则希望大家在理解的前提下进行记忆：
① [修饰符列表]，此项是可选项，不是必须的，目前大家统一写成 public static，后面的
课程会详细讲解。
② 返回值类型，此项可以是 java 语言当中任何一种数据类型，包括基本数据类型，也包括所有的引用数据类型，当然，如果一个方法执行结束之后不准备返回任何数据，则返回值类
型必须写 void。返回值类型例如：byte,short,int,long,float,double,boolean,char,String,void 等。
③ 方法名，此项需要是合法的标识符，开发规范中要求方法名首字母小写，后面每个单词首字母大写，遵循驼峰命名方式，见名知意，例如：login、getUsername、findAllUser 等。
④ 形式参数列表(int a, int b)，此项又被称为形参，其实每一个形参都是“局部变量”，形参的个数为 0~N 个，如果是多个参数，则采用半角“,”进行分隔，形参中起决定性作用的
是参数的数据类型，参数名就是变量名，变量名是可以修改的，也就是说(int a , int b)也可以写成(int x , int y)。
⑤ 方法体，由一对儿大括号括起来，在形参的后面，这个大括号当中的是实现功能的核心代码，方法体由 java 语句构成，方法体当中的代码只能遵循自上而下的顺序依次逐行执行，
不能跳行执行，核心代码在执行过程中如果需要外部提供数据，则通过形参进行获取。

整体来说方法的声明语法是很简单的，我相信每个人都能记住，其实我觉得方法的定义难度最大的不是语法，而是方法在定义的时候，返回值类型定为什么类型比较合适？方法的形式参数列表中定义几个参数合适？每个参数的数据类型定义为什么比较合适？以上的一系列问题实际上还是需要和具体的功能结合在一起才能决定，当然，这不是一天两天的事儿，不是说这一章节的内容学完之后就真正的会定义方法了，我们只能说语法会了，还需要后期不断的做项目，写代码才能找到感觉，找到编程思路。到那时，你自然就会定义返回值类型、形式参数列表了.
#### 1.7.2 方法的重载
>**重载的条件**
* 方法名相同
* 方法的参数类型，个数，顺序至少有一个不同
* 方法的返回类型可以不同（不依靠返回类型来区分重载）
* 方法的修饰符可以不同，因为方法重载和修饰符没有任何关系
* 方法重载只出现在同一个类中
```java
public class OverloadTest02 {
    public static void main(String[] args) {
        int retInt = sum(10, 20);
        System.out.println(retInt);
        float retFloat = sum(1.5f, 2.5f);
        System.out.println(retFloat);
        double retDouble = sum(2.2, 3.2);
        System.out.println(retDouble);
    }

    //对 int 求和
    public static int sum(int v1, int v2) {
        return v1+v2;
    }

    //对 float 求和
    public static float sum(float v1, float v2) {
        return v1+v2;
    }

    //对 double 求和
    public static double sum(double v1, double v2) {
        return v1+v2;
    }

    //正确
    public static double sum() {
        return 0L;
    }

    //错误，重载不依赖返回值
    //public static void sum() {
    // return 0L;
    //}

    //正确
    public static double sum(double v1, double v2, int v3) {
        return 0L;
    }
    
    //正确
    public static double sum(int v3, double v1, double v2) {
        return 0L;
    }

    //正确
    public static double sum(double v1, int v3, double v2) {
        return 0L;
    }

    //不正确
    //public static double sum(double v2, double v1) {
        // return 0L;
    //}
}
```
以上代码使用了方法重载机制，我们可以看到，三个“功能相似”的方法名字都叫做 sum，只不过方法的形参不同，这样对于程序员来说，调用方法时所需要记忆的方法名更少一些，代码更加美观
>方法重载（overload）是指在一个类中定义多个同名的方法，但要求每个方法具有不同的参数的类型或参数的个数。调用重载方法时，Java 编译器能通过检查调用的方法的参数类型和个数选择一个恰当的方法。方法重载通常用于创建完成一组任务相似但参数的类型或参数的个数不同的方法。调用方法时通过传递给它们的不同个数和类型的实参来决定具体使用哪个方法.

***代码满足什么条件的时候构成方法重载呢？满足以下三个条件***
>① 在同一个类当中。
② 方法名相同。
③ 参数列表不同：个数不同算不同，顺序不同算不同，类型不同也算不同

#### 1.7.3 方法的递归问题
>不使用递归求和
```java
public class RecursionTest01 {
    public static void main(String[] args) {
        int retValue = method1(5);
        System.out.println(retValue);
    }

    //给指定的值求和
    public static int method1(int n) {
        int s = 0;
        for (int i=1; i<=n; i++) {
            //s=s+i;
            s+=i;
        }
        return s;
    }
}
```
>使用递归求和
```java
public class RecursionTest02 {
    public static void main(String[] args) {
        int retValue = method1(5);
        System.out.println(retValue);
    }

    //采用递归求和
    public static int method1(int n) {
        if (n == 1) {
        return 1;
        }else {
        //递归调用，调用自身
        return n + method1(n-1);
        }
    }
}
```
**递归的基本思想是把规模大的问题转化为规模小的相似的子问题来解决。在函数实现时，因为解决大问题的方法和解决小问题的方法往往是同一个方法，所以就产生了函数调用它自身的情况。另外这个解决问题的函数必须有明显的结束条件，这样就不会产生无限递归的情况了。**
* 递归的应用场景
在我们实际学习工作中，递归算法一般用于解决三类问题：
1、 问题的定义是按递归定义的（Fibonacci函数，阶乘，…）；
2、问题的解法是递归的（有些问题只能使用递归方法来解决，例如，汉诺塔问题，…）；
3、数据结构是递归的（链表、树等的操作，包括树的遍历，树的深度，…）。
---
* 递归算法设计
递归的基本思想就是把规模大的问题转化为规模小的相似的子问题来解决。特别地，在函数实现时，因为解决大问题的方法和解决小问题的方法往往是同一个方法，所以就产生了函数调用它自身的情况，这也正是递归的定义所在。格外重要的是，这个解决问题的函数必须有明确的结束条件，否则就会导致无限递归的情况。
因此，若要设计一个递归的算法程序，需要认知递归三要素：
1、将一个问题化简到更小的规模，类似于数学归纳法的步骤；
2、父问题与子问题不能有重叠的部分，通过子问题的解可以解决父问题；
3、确定递归终止的条件，比如树到达叶子节点，二分查找时left等于right。


## 2 面向对象
---
### 2.1 面向对象
面向对象（Object Oriented）是一种新兴的程序设计方法，或者是一种新的程序设计规范(paradigm)，其基本思想是使用对象、类、继承、封装、多态等基本概念来进行程序设计。从现实世界中客观存在的事物（即对象）出发来构造软件系统，并且在系统构造中尽可能运用人类的自然思维方式。

### 2.2 对象
对象是系统中用来描述客观事物的一个实体，它是构成系统的一个基本单位。一个对象由一组属性和对这组属性进行操作的一组服务组成。

类的实例化可生成对象，一个对象的生命周期包括三个阶段：生成、使用、消除。

当不存在对一个对象的引用时，该对象成为一个无用对象。Java的垃圾收集器自动扫描对象的动态内存区，把没有引用的对象作为垃圾收集起来并释放。当系统内存用尽或调用System.gc( )要求垃圾回收时，垃圾回收线程与系统同步运行。

### 2.3 类
类是具有相同属性和方法的一组对象的集合，它为属于该类的所有对象提供了统一的抽象描述，其内部包括属性和方法两个主要部分。在面向对象的编程语言中，类是一个独立的程序单位，它应该有一个类名并包括属性和方法两个主要部分。

Java中的类实现包括两个部分：类声明和类体。

**类声明**
```java
[public][abstract|final] class className [extends superclassName] [implements interfaceNameList]{……}
```
其中，修饰符public,abstract,final 说明了类的属性，className为类名，superclassName为类的父类的名字interfaceNameList为类所实现的接口列表。

**类体**

```java
class className{
    [public | protected | private ] [static] [final] [transient] [volatile] type variableName;//成员变量
    [public | protected | private ] [static] [final | abstract] [native] [synchronized] returnType methodName([paramList]) [throws exceptionList]{
        statements
    }//成员方法
}
```
成员变量限定词的含义：
1. static: 静态变量（类变量）
2. final: 常量；transient: 暂时性变量，用于对象存档，用于对象的串行化
3. volatile: 贡献变量，用于并发线程的共享

方法的实现也包括两部分内容：方法声明和方法体。

**方法声明**

方法声明中的限定词的含义：

1. static: 类方法，可通过类名直接调用
2. abstract: 抽象方法，没有方法体
3. final: 方法不能被重写
4. native: 集成其它语言的代码
5. synchronized: 控制多个并发线程的访问

方法声明包括方法名、返回类型和外部参数。其中参数的类型可以是简单数据类型，也可以是复合数据类型（又称引用数据类型）。
对于简单数据类型来说，java实现的是值传递，方法接收参数的值，但不能改变这些参数的值。如果要改变参数的值，则用引用数据类型，因为引用数据类型传递给方法的是数据在内存中的地址，方法中对数据的操作可以改变数据的值。

**方法体**

方法体是对方法的实现，它包括局部变量的声明以及所有合法的Java指令。方法体中声明的局部变量的作用域在该方法内部。若局部变量与类的成员变量同名，则类的成员变量被隐藏。
为了区别参数和类的成员变量，我们必须使用this。this用在一个方法中引用当前对象，它的值是调用该方法的对象。返回值须与返回类型一致，或者完全相同，或是其子类。当返回类型是接口时，返回值必须实现该接口。

**构造方法**

* 构造方法是一个特殊的方法。Java 中的每个类都有构造方法，用来初始化该类的一个对象。
* 构造方法具有和类名相同的名称，而且不返回任何数据类型。
* 重载经常用于构造方法。
* 构造方法只能由new运算符调用

### 2.4 面向对象的基本特性
---
>面向对象具体有三大特性，分别为：封装、继承、多态。
---
#### 2.4.1 封装

封装性就是尽可能的隐藏对象内部细节，对外形成一道边界，只保留有限的接口和方法与外界进行交互。封装的原则是使对象以外的部分不能随意的访问和操作对象的内部属性，从而避免了外界对对象内部属性的破坏。

可以通过对类的成员设置一定的访问权限，实现类中成员的信息隐藏。

* private：类中限定为private的成员，只能被这个类本身访问。如果一个类的构造方法声明为private,则其它类不能生成该类的一个实例。
* default：类中不加任何访问权限限定的成员属于缺省的（default）访问状态，可以被这个类本身和同一个包中的类所访问。
* protected：类中限定为protected的成员，可以被这个类本身、它的子类（包括同一个包中以及不同包中的子类）和同一个包中的所有其他的类访问。
* public：类中限定为public的成员，可以被所有的类访问。

|   | private| default| protected| public|
|---|--------|--------|----------|-------|
| 同一类中  |  √  |  √  |   √  |  √  |
| 同一包中  |     |  √  |   √  |  √  |
| 子类      |     |     |   √  |  √  |
| 全局范围  |     |     |      |  √  |

#### 2.4.2 继承

子类的对象拥有父类的全部属性与方法，称作子类对父类的继承

>* Java中父类可以拥有多个子类，但是子类只能继承一个父类，称为单继承。
>* 继承实现了代码的复用。
>* Java中所有的类都是通过直接或间接地继承java.lang.Object类得到的。
>* 子类不能继承父类中访问权限为private的成员变量和方法。
>* 子类可以重写父类的方法，即命名与父类同名的成员变量。

Java中通过super来实现对父类成员的访问，super用来引用当前对象的父类。super 的使用有三种情况：
>* 访问父类被隐藏的成员变量，如：super.variable;
>* 调用父类中被重写的方法，如：super.Method([paramlist]),super()调用父类构造方法;
>* 调用父类的构造函数，如：super([paramlist]);

#### 2.4.3 多态

对象的多态性是指在父类中定义的属性或方法被子类继承之后，可以具有不同的数据类型或表现出不同的行为。这使得同一个属性或方法在父类及其各个子类中具有不同的语义。例如："几何图形"的"绘图"方法，"椭圆"和"多边形"都是"几何图"的子类，其"绘图"方法功能不同。

Java的多态性体现在两个方面：由方法重载实现的静态多态性（编译时多态）和方法重写实现的动态多态性（运行时多态）。

>* 编译时多态：在编译阶段，具体调用哪个被重载的方法，编译器会根据参数的不同来静态确定调用相应的方法。
>* 运行时多态：由于子类继承了父类所有的属性（私有的除外），所以子类对象可以作为父类对象使用。程序中凡是使用父类对象的地方，都可以用子类对象来代替。一个对象可以通过引用子类的实例来调用子类的方法。

#### 2.4.4 重载

* 方法重载是让类以统一的方式处理不同数据类型的手段。
* 一个类中可以创建多个方法，它们具有相同的名字，但具有不同的参数和不同的定义。调用方法时通过传递给它们的不同参数个数和参数类型来决定具体使用哪个方法。
* 返回值类型可以相同也可以不相同，无法以返回型别作为重载函数的区分标准。

#### 2.4.5 面向对象重要内容总结
---

##### 2.4.5.1 final关键字

    final 表示不可改变的

* 采用 final 修饰的类不能被继承
```java
public class FinalTest01 {
    public static void main(String[] args) {

    }
}
final class A1 {
    public void test1() {
        
    }
}

//不能继承 A1，因为 A1 采用 final 修饰了
class B1 extends A1 {
    public void test2() {

    }
}

```

* 采用 final 修饰的方法不能被覆盖
```java
public class FinalTest02 {
    public static void main(String[] args) {
        
    }
}
class A1 {
    public final void test1() {

    }
}
class B1 extends A1 {
    //覆盖父类的方法，改变其行为
    //因为父类的方法是 final 修饰的，所以不能覆盖
  //  public void test1() {
  //
  //  }

    public void test2() {

    }
}
```

* 采用 final 修饰的变量不能被修改

```java
public class FinalTest03 {

    private static final long CARD_NO = 878778878787878L;

    public static void main(String[] args) {
        //不能进行修改，因为 CARD_NO 采用 final 修改了
        CARD_NO = 99999999999999L;
    }
}
```

* final 修饰的变量必须显示初始化

```java
public class FinalTest04 {

    //如果是 final 修饰的变量必须初始化

    private static final long CARD_NO = 0L;

    public static void main(String[] args) {
        int i;

        //局部变量必须初始化
        //如果不使用可以不初始化
        System.out.println(i);
    }
}
```

* 如果修饰的引用，那么这个引用只能指向一个对象，也就是说这个引用不能再次赋值，但被指向的对象是可以修改的

```java
public class FinalTest05 {
    public static void main(String[] args) {
        Person p1 = new Person();
        //可以赋值
        p1.name = "张三"; 
        System.out.println(p1.name);

        final Person p2 = new Person();
        p2.name = "李四";
        System.out.println(p2.name);
        //不能编译通过
        //p2 采用 final 修饰，主要限制了 p2 指向堆区中的地址不能修改(也就是p2 只能指向一个对象)

        //p2 指向的对象的属性是可以修改的
        p2 = new Person();
    }
}
//
class Person {
    String name;
}

```
* 构造方法不能被 final 修饰
* 会影响 JAVA类的初始化:final 定义的静态常量调用时不会执行 java 的类初始化方法，也就是说不会执行 static 代码块等相关语句，这是由 java 虚拟机规定的。我们不需要了解的很深，有个概念就可以了

##### 2.4.5.2 抽象类

看我们以前示例中的 Person、Student 和 Employee，从我们使用的角度来看主要对 Student 和Employee 进行实例化，Person 中主要包含了一些公共的属性和方法，而Person 我们通常不会实例化，所以我们可以把它定义成抽象的：
>* 在 java 中采用 abstract 关键字定义的类就是抽象类，采用 abstract 关键字定义的方法就是抽象方法
>* 抽象的方法只需在抽象类中，提供声明，不需要实现
>* 如果一个类中含有抽象方法，那么这个类必须定义成抽象类
>* 如果这个类是抽象的，那么这个类被子类继承，抽象方法必须被重写。如果在子类中不复写该抽象方法，那么必须将此类再次声明为抽象类
>* 抽象的类是不能实例化的，就像现实世界中人其实是抽象的，张三、李四才是具体的
>* 抽象类不能被 final 修饰
>* 抽象方法不能被 final 修饰，因为抽象方法就是被子类实现的

抽象类中可以包含方法实现，可以将一些公共的代码放到抽象类中，另外在抽象类中可以定义一些抽象的方法，这样就会存在一个约束，而子类必须实现我们定义的方法，如：teacher 必须实现 printInfo 方法，Student 也必须实现printInfo 方法，方法名称不能修改，必须为 printInfo，这样就能实现多态的机制，有了多态的机制，我们在运行期就可以动态的调用子类的方法。所以在运行期可以灵活的互换实现。

>1. 采用 abstract 声明抽象类
```java
public class AbstractTest01 {
    public static void main(String[] args) {
        //不能实例化抽象类
        //抽象类是不存在，抽象类必须有子类继承
        Person p = new Person();
        //以下使用是正确的，因为我们 new的是具体类
        Person p1 = new Employee();
        p1.setName("张三");
        System.out.println(p1.getName());
    }
}
//采用 abstract 定义抽象类
//在抽象类中可以定义一些子类公共的方法或属性
//这样子类就可以直接继承下来使用了，而不需要每个
//子类重复定义
abstract class Person {
    private String name;
    public void setName(String name) {
        this.name = name;
    }
    public String getName() {
        return name;
    }
    //此方法各个子类都可以使用
    public void commonMethod1() {
        System.out.println("---------commonMethod1-------");
    }
}
class Employee extends Person {

}
class Student extends Person {

}
```

>2. 抽象的方法只需在抽象类中，提供声明，不需要实现，起到了一个强制的约束作用，要求子类必须实现
```java
public class AbstractTest02 {
    public static void main(String[] args) {
        //Person p = new Employee();
        //Person p = new Student();
        //Person p = new Person();
        p.setName("张三");
        p.printInfo();
    }
}
abstract class Person {
    private String name;
    public void setName(String name) {
        this.name = name;
    }
    public String getName() {
        return name;
    }
    //此方法各个子类都可以使用
    public void commonMethod1() {
        System.out.println("---------commonMethod1-------");
    }
    //public void printInfo() {
        // System.out.println("------Person.printInfo()--------");
    //}
    //采用 abstract 定义抽象方法
    //如果有一个方法为抽象的，那么此类必须为抽象的
    //如果一个类是抽象的，并不要求具有抽象的方法
    public abstract void printInfo();
}
class Employee extends Person {
    //必须实现抽象的方法
    public void printInfo() {
        System.out.println("Employee.printInfo()");
    }
}
class Student extends Person {
    //必须实现抽象的方法
    public void printInfo() {
        System.out.println("Student.printInfo()");
    }
}
```

>3. 如果这个类是抽象的，那么这个类被子类继承，抽象方法必须被覆盖。如果在子类中不覆盖该抽象方法，那么必须将此方法再次声为抽象方法

```java
public class AbstractTest03 {
    public static void main(String[] args) {
        //此时不能再 new Employee 了
        Person p = new Employee();
    }
}
abstract class Person {
    private String name;
    public void setName(String name) {
        this.name = name;
    }
    public String getName() {
        return name;
    }
    //此方法各个子类都可以使用
    public void commonMethod1() {
        System.out.println("---------commonMethod1-------");
    }
    //采用 abstract 定义抽象方法
    public abstract void printInfo();
}
abstract class Employee extends Person {
    //再次声明该方法为抽象的
    public abstract void printInfo();
}
class Student extends Person {
    //实现抽象的方法
    public void printInfo() {
        System.out.println("Student.printInfo()");
    }
}
```

