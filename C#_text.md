[返回首页](../index.html)

# C#学习笔记——***By Bug***

笔记开始时间：2024.1.26
笔记更新时间：2024.2.22
当前笔记状态：基础篇已完结，高级篇暂不更新

前言

*你好：*

​	*首先感谢你使用这份笔记手册，一起学习，一起进步，本学习笔记是我在自学过程（网课视频在下方链接）中的随手笔记，可能出现遗漏，顺序错误或语法，单词等错误，你可以在自己的学习过程中对这份笔记更正即可。*

笔记结合了多个网课资料，顺序较为混乱。

下面是笔记部分参考资料：
视频资料： https://www.bilibili.com/video/BV1gR4y1b7oW/?p=6&share_source=copy_web&vd_source=ea0cf64e8dac6f0193a7e28187a0fccb

c#官方文档：[C# 文档 - 入门、教程、参考。 | Microsoft Learn](https://learn.microsoft.com/zh-cn/dotnet/csharp/)

前言到此结束。下面是笔记部分：

---

## Visual Studio 下载与安装

### 下载

社区版下载地址[Visual Studio Community Edition (microsoft.com)](https://visualstudio.microsoft.com/zh-hans/thank-you-downloading-visual-studio/?sku=Community&channel=Release&version=VS2022&source=VSLandingPage&cid=2030&passive=false)

### 安装

请参考vs官方安装教程：
[安装 Visual Studio 并选择首选功能 | Microsoft Learn](https://learn.microsoft.com/zh-cn/visualstudio/install/install-visual-studio?view=vs-2022)

![image-20240126163837786](./imgs/image-20240126163837786.png)

## C#编程基础语法

注意：

1. C#是大小写敏感的
2. 所有的语句表达式都必须以（;）结尾
3. 与Java不同的是，文件名可以不与类的名称相同

### cs文件结构

```c#
//引用命名空间
using ConsoleApp1;
using System;
using System.Reflection.Metadata.Ecma335;
//项目命名空间，大多数也是项目本身的名称
namespace learn { 
    //类名称
    class program
    {
        //方法（函数）
        static void Main()
        {
           //方法体，用于写具体方法代码
        }
    }
}
```

### 关键字 

关键字是对编译器有特殊意义的预定保留标识符，不能在程序中用作标示符



### 注释

- 单行：//注释内容

- 多行：/\*注释内容\*/

- 注释快捷键（组合键）：ctrl+k ,ctrl+c

- 解除多行注释：CTRL+k,ctrl+u

- 输出第一个程序Hello World

  ```c#
  Console.WriteLine("Hello, World!");
  ```

  Console.Write和Console.WriteLine区别：Console.WriteLine书写完后会换行，而write不会换行；

### 变量

#### 数据类型

![image-20240127102057966](./imgs/image-20240127102057966.png)

|    类型    |          举例          |
| :--------: | :--------------------: |
|  整数类型  | byte、short、int、long |
|  浮点类型  |     float、double      |
| 十进制类型 |        decimal         |
|  布尔类型  |          bool          |
|  字符类型  |      string、char      |
|   空类型   |          null          |



#### 创建赋值变量

```c#
//创建变量
//数据类型+变量名，例如
int age;
string abc;
char str
//变量赋值
age=12;
abc = "aaa";
```



#### 字符类型

​	每个字符在存储时都对应一个数字![825b9894ae154cffbdb6ffab7bd67261](./imgs/825b9894ae154cffbdb6ffab7bd67261.png)

#### 

数字与字符之间转换的方法

```c#
//字母转数字
char a='a';
int b =a;
Console.WriteLine(b);
//数字转字母
int a=97;
char b =(char)a;
Console.WriteLine(b);
```

#### 字符串拼接

```c#
//打印字符串防止转义字符生效
Console.WriteLine(@"c:\a\vc\v1");
//字符串声明和拼接
string a = "a";
string b = "b";
Console.WriteLine(a+b);
    
```

#### 字符串格式化输出

```c#
int a = 10, b = 20;
Console.WriteLine("和为:{0}+{1}={2}",a,b,a+b);
//a,b,a+b 下标为0，1，2所以写为：
```



### 获取输入

```c#
//返回的值为字符串。
Console.ReadLine();
//将获取的字符串类型的数字转换成int类型
Convert.ToInt32();
```

获取一个数字，并转换为int类型

```c#
string b="";
Console.WriteLine("请输入一个数");
b=Console.ReadLine();
Convert.ToInt32(b);
Console.WriteLine(b);
```

#### 

## C#语法进阶

### 运算符

#### 算数运算符

- +, -, *, /, *

#### 逻辑运算符

- 逻辑与：&&
- 逻辑或：||
- 逻辑非：！

#### 关系运算符

(   >，<，>=，<=，==)

#### 三元运算符

x?y:z -->如果为true，则取y的值，如果为false，则取z的值

---

### 流程控制

#### 分支语句（if）

```c#
if (条件1){
    //语句;满足条件时执行
}
else if(条件2){
    //语句
}
else{
    //语句
}
```

#### 分支语句（switch-case ）

```c#
switch(变量)
{
        case 值1:{
           contun
        };
        case 值2:{
            break;
        };
    	case 值3:{
            break;
        }
        default: {
            //默认情况
        }
};
```

#### 循环语句（while）

```c#
//语法
while(条件){
    
}
//创建一格死循环
while(true){
    //语句
}
while(1){
    //语句
}
//打印输出乘法表 
int i = 1, j = 1;
 while (i<=9)
 {
     while (j <= i)
     {
         Console.Write("{1}×{0}={2}\t",i,j,j*i);
         j++;
         if (j > i)
         {
             Console.WriteLine();
             j = 1;
             i++;
             break;
         }
     }
 }
```

#### 循环语句（for）

```c#
//语法
for(初始值;条件表达式;增量表达式){
    //语句
};
```

#### 循环语句（do-while）

```c#
// 语法
do{

}while(条件表达式)
```

### 数组

#### 数组的声明

```c#

//类型[] 数组名={};
//声明
int[5] num;
int[] num2;
//赋值
int[] num3 = { 1, 2, 3, 4, 5 };
num2 = new int[100];//创建一个长度为100的数组
num =new int[] {1,2,3,4,5}
//数组使用时用下标
```

#### 数组遍历

```c#
//方法1
//使用for/while循环 
int[] num = { 1, 2, 3, 4, 5 };
for (int i = 0; i < num.Length; i++)
{
    Console.WriteLine(num[i]);  
}
//方法2
//使用foreach(只能)
int[] num = { 1, 2, 3, 4, 5 };
foreach (int item in num)
{
    Console.WriteLine(item);
}


```

#### 字符数组

```c#
 string str = "abcdefghijklmnopqrstuvwxyz";

 for (int i = 0; i < str.Length; i++)
 {
     Console.WriteLine(str[i]);
 }
```

#### 字符串操作方法

1. ToLower()——转换成小写字母、
   ToUpper()——转换成大写字母

2. Trim()——去除字符串两端的空格
   TrimStrat()——去除字符串前端的空格
   TrimEnd()——去除字符串后端的空格 

3. Split()——分割方法

   [使用 String.Split 拆分字符串（C# 指南） - C# | Microsoft Learn](https://learn.microsoft.com/zh-cn/dotnet/csharp/how-to/parse-strings-using-split)

   下方代码将一个常用短语拆分为一个由每个单词组成的字符串数组。

   ```c#
   string phrase = "The quick brown fox jumps over the lazy dog.";
   string[] words = phrase.Split(' ');
   
   foreach (var word in words)
   {
       System.Console.WriteLine($"<{word}>");
   }
   ```

   分隔符的每个实例都会在返回的数组中产生一个值。 连续的分隔符将生成空字符串作为返回的数组中的值。 下面的示例介绍如何创建空字符串，该示例使用空格字符作为分隔符。

   ```c#
   string phrase = "The quick brown    fox     jumps over the lazy dog.";
   string[] words = phrase.Split(' ');
   
   foreach (var word in words)
   {
       System.Console.WriteLine($"<{word}>");
   }
   ```

   [String.Split](https://learn.microsoft.com/zh-cn/dotnet/api/system.string.split) 可使用多个分隔符。 下面的示例使用空格、逗号、句点、冒号和制表符作为分隔字符，这些分隔字符在数组中传递到 [Split](https://learn.microsoft.com/zh-cn/dotnet/api/system.string.split)。 代码底部的循环显示返回数组中的每个单词。

   ```c#
   char[] delimiterChars = { ' ', ',', '.', ':', '\t' };
   
   string text = "one\ttwo three:four,five six seven";
   System.Console.WriteLine($"Original text: '{text}'");
   
   string[] words = text.Split(delimiterChars);
   System.Console.WriteLine($"{words.Length} words in text:");
   
   foreach (var word in words)
   {
       System.Console.WriteLine($"<{word}>");
   }
   ```

   [String.Split](https://learn.microsoft.com/zh-cn/dotnet/api/system.string.split) 可采用字符串数组（充当用于分析目标字符串的分隔符的字符序列，而非单个字符）。

   ```c#
   string[] separatingStrings = { "<<", "..." };
   
   string text = "one<<two......three<four";
   System.Console.WriteLine($"Original text: '{text}'");
   
   string[] words = text.Split(separatingStrings, System.StringSplitOptions.RemoveEmptyEntries);
   System.Console.WriteLine($"{words.Length} substrings in text:");
   
   foreach (var word in words)
   {
       System.Console.WriteLine(word);
   }
   ```

## 函数   

#### 定义

```c#
static 返回类型 函数名(参数){
    //语句
}
```

#### 使用

```c#
函数名();
```

#### 参数

```c#
static 返回类型 函数名(类型 参数名（形参）){
    //语句
}
```

形参（形式参数）

在函数定义中出现的参数可以看做是一个占位符，它没有数据，只能等到函数被调用时接收传递进来的数据，所以称为**形式参数**，简称**形参**。

实参（实际参数）

函数被调用时给出的参数包含了实实在在的数据，会被函数内部的代码使用，所以称为**实际参数**，简称**实参**。

形参和实参的功能是传递数据，发生函数调用时，实参的值会传递给形参。

形参和实参的区别和联系

1) 形参变量只有在函数被调用时才会分配内存，调用结束后，立刻释放内存，所以形参变量只有在函数内部有效，不能在函数外部使用。

2) 实参可以是常量、变量、表达式、函数等，无论实参是何种类型的数据，在进行函数调用时，它们都必须有确定的值，以便把这些值传送给形参，所以应该提前用赋值、输入等办法使实参获得确定值。

3) 实参和形参在数量上、类型上、顺序上必须严格一致，否则会发生“类型不匹配”的错误。当然，如果能够进行自动类型转换，或者进行了强制类型转换，那么实参类型也可以不同于形参类型。

4) 函数调用中发生的数据传递是单向的，只能把实参的值传递给形参，而不能把形参的值反向地传递给实参；换句话说，一旦完成数据的传递，实参和形参就再也没有瓜葛了，所以，在函数调用过程中，形参的值发生改变并不会影响实参。

#### 参数修饰符

修饰符种类

1. 无修饰符：如果一个参数没有油参数修饰符标记，则认为它将***按值传递***，这将意味着被调用的方法收到原始数据的一份副本；
2. out：输出参数由被调用的方法赋值，因此按***引用传递***。如果被调用的方法没有给输出的参数赋值，就会出现编译错误。（下端数据被修改后，上端数据也会随之变化）
   out最大的用途就是调用者只使用一次方法就能获得多个返回值。
3. ref：调用者赋初值，并且可以由被调用的方法可选的重新赋值（数据也是按引用传递）。如果被调用的方法未能给ref参数赋值，也不会有编译错误。
4. 其他请参见官方文档：[方法参数按值传递。 修饰符启用按引用传递语义，包括只读和 `out` 参数等区别。 了解不同的参数传递模式以及如何使用它们。 参数修饰符允许一系列可选参数。 - C# | Microsoft Learn](https://learn.microsoft.com/zh-cn/dotnet/csharp/language-reference/keywords/method-parameters)

#### 返回值

```c#
static 返回类型 函数名(类型 参数名（形参）){
    //语句
    return 返回值;	//使用return返回
}
//接受返回值方法
//定义变量=函数名();
```

参数数组

```c#
//参数数组传参方式
static int sums(int[] array)
{
    //for循环遍历数组计算
    return sum;
}

```



##### 案例

```c#
static int sum(int x,int y) {
return  x + y;

}
Console.WriteLine(sum(11111,2232123));

//参数数组
//计算任意个数的和
static int sums(int[] array)
{
    int sum = 0;
    for (int i = 0; i < array.Length; i++)
    {
        sum += array[i];
    }
    return sum;
}
int[] a = {1,2,3,4,5,6,7,8,9,10};
Console.WriteLine(sums(a));
```

#### 函数重载-overload

重载，简单说，就是函数或者方法有相同的名称，但是参数列表不相同的情形，这样的同名不同参数的函数或者方法之间，互相称之为重载函数或者方法。
重载的定义:函数名相同,函数的参数列表不同(包括参数个数和参数类型)，至于返回类型可同可不同。
重载是可使函数、运算符等处理不同类型数据或接受不同个数的参数的一种方法

#### 递归函数

在函数的内部再次调用这个函数。

##### 案例

```c#
// f(n)=f(n-1)+f(n-2),其中f(0)=2,f(1)=3
  
           static int f(int n)
            {
                if (n == 0)
                {
                    return 2;
                }
                else if (n == 1)
                {
                    return 3;
                }
                else
                {
                    int fn = f(n - 1) + f(n - 2);
                    return fn;
                }
                
            }
            Console.WriteLine(f(40));
```

### 常量

```c#
const int HP = 100;
```

### 枚举类型

Enum枚举:枚举是一组命名整型常量,枚举类型是使用 enum 关键字声明的。枚举是值类型，数据直接存储在栈中，而不是使用引用和真实数据的隔离方式来存储,其包含自己的值,且不能被继承或者传递继承,枚举中每个元素的基础类型是 int。可以使用冒号指定另一种整数值类型。

定义与使用枚举类型

```c#
//定义
enum names
{
    抽烟, 喝酒, 烫头
};

static void Main()
{
	//使用  
    Console.WriteLine(names.烫头);
}
```

### 结构体

​	结构体的作用就是把某一类的变量进行整合，组成一个新的数据类型，比如学生的信息（姓名，性别，年龄，成绩等等）

结构体的定义和使用

```c#
//定义
struct <name>{
    //访问权限 type name;
}
//使用
struct student
{
    public string name;
    public int age;
    public char sex;
    public int id;
}
static void Main()
{
    //单个学生
    student student1;
    student1 = new student();//实例化
    student1.name = "张三";
    student1.age = 19;
    student1.sex = 'B';
    student1.id = 1000101;
    //多个学生可使用数组管理
    student[] somestudent = new student[100];
    somestudent[0].age = 19;
    somestudent[1].age = 19;
    somestudent[2].age = 19;
    somestudent[0].name = "詹西西";

}
```

结构体中不只是可以定义属性，也可以定义函数。

```c#
struct student
{
    public string name;
    public int age;
    public char sex;
    public int id;
    public void print()
    {
       Console.WriteLine(name + " " + age+);
    }
}
student student1;
student1 = new student();
student1.name = "张三";
student1.age = 19;
student1.sex = 'B';
student1.id = 1000101;
student1.print();
```



### 委托

**委托（Delegate）** *是存有对某个方法(函数)的引用的一种引用类型变量。引用可在运行时被改变。*

```c#
static int jia(int a,int b)
{

    return a+b;
}
static int jian(int a, int b)
{
    return a - b;
}
static int cheng(int a, int b)
{
    return a * b;
}
static int chu(int a, int b)
{
    return a / b;
}
//定义委托
delegate int soms(int a, int b);
static void Main()
{
    //委托声明
    soms weituo;
    weituo = add;
    Console.WriteLine(weituo(10, 2));

}
// 开发时使用
delegate void whendie();
//程序员1
static void play(whendie tip)
{
    Console.WriteLine("正在打仗");
    tip();
}
//程序员2
static void stop() 
{ 
    Console.WriteLine("失败，死亡了");
}
static void win() { Console.WriteLine("胜利了"); }

static void Main()
{
    play(win);

}

```

## 面向对象（OOP）

### 面向对象介绍

C# 是面向对象的编程语言。 面向对象编程的四项基本原则为：

- 抽象：将实体的相关特性和交互建模为类，以定义系统的抽象表示。
- 封装：隐藏对象的内部状态和功能，并仅允许通过一组公共函数进行访问。
- 继承：根据现有抽象创建新抽象的能力。
- 多形性：跨多个抽象以不同方式实现继承属性或方法的能力。

面向对象就是一种编码的思想，简称(oop思想)，这种编程思想可以让你在编码的过程中，对于类的使用变得更加的方便快捷，在不同的场合使用不同的类和对象，会让你的程序维护起来更加方便

### 异常捕捉

```c#
//try中放置可能出现异常的代码
try{
    //代码
}
//捕获到异常时执行
catch(要捕获的异常){
    //代码
}
//不管代码是否出现异常，代码都会执行
finally{
    //代码
}
```

```c#
//使用try-catch检查用户输入是否合法
 while (true) { 
 try {
     int a = Convert.ToInt32(Console.ReadLine());            
     int b = Convert.ToInt32(Console.ReadLine());
     break;
 } 
 catch (System.FormatException) {
     Console.WriteLine("你的输入不合法");
 }
 }
```

注意：再try块中的代码如果某一行出现了异常，后面的代码就不会再执行了，会跳到catch中。

### 类

#### 类的定义

类是对一类具有相同特征或行为的事务的统称，是抽象的，不能直接使用

- 特征被称为：属性
- 行为被称为：方法

类相当于模板
对象 相当于由模板创造出来的实物

```c#
class 类名
{

}
类名 name =new 类名();
```

#### 类的使用

```c#
//定义一个类  
class student
 {
     public long Id;
     public string Name;
     public int Age;
 }
static void Main()
 {
    student C1 = new student();//实例化类赋值
     C1.Id = 202221345612;
     C1.Name = "Test";
     C1.Age = 19;
 }
```

#### 声明属性

- 属性在C#中较为独特，它即不同于方法，也不同于字段。
- 属性依旧遵循大驼峰命名法
- 属性最常用的书写方法：public int age {get; set;}
- 如果属性中具有get关键字，说明可以获取该属性的值
- 如果属性中具有set关键字，说明可以设置该属性的值



### 集合&字典

#### ArrayList-动态数组

```c#
using System.Collections;
namespace WinFormsApp1
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }
        
        private void Form1_Load(object sender, EventArgs e)
        {
            ArrayList arrayList = new ArrayList();
        }
    }
}
//ArrayList相关方法
//ArrayList.add --在结尾处添加数据
//ArrayList[-] --修改"-"处的数据
//ArrayList.RemoveAt(-) --移除“-”索引处的数据
//ArrayList.Remove(123) --移除内容为123的数据
//ArrayList.Insert(-,"hello")在索引“-”处插入数据

```

#### List数组

```c#
//list数组声明，在声明List数组时，需要再<>中添加数据类型，如int,string 等；指定存储的数据类型
List<int> list_name=new List<int>;
// 示例
List<int> list1 = new List<int>();
list1.Add(1);
list1.Add(2);
list1.Add(3);
list1.Add(4);
list1.Add(5);
for (int i = 0; i < list1.Count; i++)
{
    Console.WriteLine(list1[i]);

}
//List数组也支持自定义的数据类型
```

- 集合与数组较为类似，都是存储的一组值；
- 集合中提供了特定的方法，能直接操作集合中的数据，并提供了不同的集合类来实现特定的功能。
- 简单来说就是数组的升级版，可以动态对集合的长度进行定义和维护。
- List泛型的好处指通过允许指定泛型类或方法操作的指定类型，减少了类型的强制转换的需要和运行时的错误的可能性，泛型提供了类型安全

#### 字典

```c#
Dictionary<int,string> student=new Dictionary<int,string>();
student.Add(20241101, "张ad");
student.Add(20241102, "张er");
student.Add(20241103, "张gt");
student.Add(20241104, "张ff");
//
public string name { get; set; }

        public int Age{ get; set; }
        
        public int outs { get; set;}
        public void show() {
            Console.WriteLine("姓名：{0}\n年龄：{1}\n出生年：{2}",name, Age,outs);
        }
Dictionary<int,Class1> student=new Dictionary<int,Class1>();
student.Add(20241101, new Class1
{
    name = "text1",
    Age = 19,
    outs=2024

}) ;

foreach (var pair in student)
{
    Console.WriteLine("学生信息：");
    Console.WriteLine("学号：{0}", pair.Key);
    pair.Value.show();
    Console.WriteLine();
}s
```

- 键与值可以是任何类型，键必须是唯一的，值可以不唯一
- 使用Add方法添加键值对时，不能添加已有键名
- 索引模式可以新赋值，也可以修改已有键值
- 索引值中写的不是索引下标，而是KEY

#### foreach遍历

```c#
foreach (var pair in student)
{
    //每次循环获取studen字典中的一个值并赋值给pair
}s
```



### 构造函数

基本类型默认值
	值类型的默认值：0
	引用类型的默认值：null

构造函数是一种方法，其名称与其类型的名称相同。 其方法签名仅包含可选[访问修饰符](https://learn.microsoft.com/zh-cn/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)、方法名称和其参数列表；它不包含返回类型。 

构造函数在new实例化时会被调用。

一般构造函数是对数据进行初始化的。

```c#
 class Student
{
    public int Id;
    public string Name;
    public int Age;
     //有参构造函数
    public Student(int date1,string date2,int date3) {
        Id = date1;
        Name = date2;
        Age = date3;
    }
     ///无参构造函数
    public Student() {
        Console.WriteLine("ID:" + Id);
        Console.WriteLine("Name:" + Name);
        Console.WriteLine("Age:" + Age);
    }
    public void show()
    {
        Console.WriteLine("ID:" + Id);
        Console.WriteLine("Name:" + Name);
        Console.WriteLine("Age:" + Age);

    }
    static void Main()
{
    //声明时调用有参构造函数
    Student C1 = new Student(202224334,"张三",19);
	//声明时调用无参构造函数
    Student C2 = new Student();
    C1.show();

}
```

### 属性

```c#
 class Student
{
    private int Id;
    private string Name;
    private int Age;
    public int ID
    {
        //get和set可以一个，为只读或只写，可以单独控制get，set访问权限
        get { return Id; }
        set { Id = value; }
    }
    public string NAME
    {
        get {return Name; }
        set { Name = value; }
    }
    public int AGE
    {
        get { return Age; }
        set { Age = value; }
    }
     //使用下面的语句系统会自动为我们创建数据成员
     public int Addres
    {
        get;
        set;
    }
     //1
     public void show()
    {
        Console.WriteLine("ID:" + Id);
        Console.WriteLine("Name:" + Name);
        Console.WriteLine("Age:" + Age);

    }
}
     static void Main()
 {
   Student lisir = new Student();{
     ID = 1;
     NAME = "LISI";
     AGE = 19;
   };
    
     Console.WriteLine("ID:" + lisir.ID);
        Console.WriteLine("Name:" +lisir.NAME);
        Console.WriteLine("Age:" + lisir.AGE);

 }
```

#### 匿名类型

```c#
//一般定义变量时
int age =1;
string name = "zhangsan";
//匿名类型(只声明了一个变量名，不指定类型，在进行初始化时会确定类型，确定就不能修改了)
var age=1;
var name="张三";
```

### 程序内存区域

#### 栈

栈的空间较小，但读取速度较快；
栈（Stack）是只允许在一端进行插入或删除操作的线性表。

![20210419182305159](./imgs/20210419182305159.png)

栈中的数据只能从顶端插入和删除
把数据放入栈顶称为入栈(push)。
把数据从栈顶删除称为出栈（pop）。
-后进先出原则；

#### 堆

堆的空间较大，但读取速度较慢；

堆是一块内存区域，堆里的内存能够以任意顺序存入和移除



#### 静态存储区

常量区（特殊的常量存储区，属于静态存储区）

　　1) 常量占用内存,只读状态,决不可修改

　　2) 常量字符串就是放在这里的，程序结束后由系统释放

#### 值类型

基本数据类型 基本数据类型常被称为四类八种。

四类八种：

- [整型](https://so.csdn.net/so/search?q=整型&spm=1001.2101.3001.7020)（4种）：byte(1 byte)、short(2 byte)、int(4 byte)、long(8 byte)
- 浮点型（2种）：float(4 byte)、double(8 byte)
- 字符型（1种）：char(2 byte)
- 逻辑型（1种）：boolean



#### 引用类型

(string,数组,自定义的类，内置的类)
引用类型需要两端内存。
	第一段用于存储实际的数据，它总是在堆中。
	第二段是一个引用，指向数据在堆中存放的位置。

值类型与引用类型的区别

![20171025115141271](./imgs/20171025115141271.png)

### 类继承

#### 什么是继承？

​	继承是面向对象程序设计中最重要的概念之一。继承允许我们根据一个类来定义另一个类，这使得创建和维护应用程序变得更容易。同时也有利于重用代码和节省开发时间。
​	当创建一个类时，程序员不需要完全重新编写新的数据成员和成员函数，只需要设计一个新的类，继承了已有的类的成员即可。这个已有的类被称为的**基类**，这个新的类被称为**派生类**。
C# 和 .NET 只支持*单一继承*。 也就是说，类只能继承自一个类。 不过，继承是可传递的。这样一来，就可以为一组类型定义继承层次结构。
​	比如在一个游戏中，两个人物的类中都具有很多相同的属性，这时我们可以让这两类继承同一个类

```c#
//继承代码演示
//基类
class Class1
    {
        public string name { get; set; }

        public int Age{ get; set; }
        
        public int outs { get; set;}
        public void show() {
            Console.WriteLine("姓名：{0}\n年龄：{1}\n出生年：{2}",name, Age,outs);
        }
    }
//派生类：继承基类
 class son_Class2:Class1
    {
        public int math {get; set;}
        public int english { get; set;}
        //重写show方法
        public void show()
        {
            Console.WriteLine("姓名：{0}\n年龄：{1}\n出生年：{2}\n数学：{3}\n英语：{4}", name, Age, outs,math,english);
        }
    }
//声明调用
son_Class2 son_Class1 = new son_Class2() { 
Age=12,
name="tex1",
outs=2022,
math=70,
english=77
};


son_Class1.show();
```

this方法--访问派生类数据成员

base方法--访问基类数据成员

#### 派生类重写方法

##### 虚方法(Virtual)

`virtual` 修饰符不能与 `static`、`abstract``private` 或 `override` 修饰符一起使用。 
`virtual` 关键字用于修改方法、属性、索引器或事件声明，并使它们可以在派生类中被重写。 例如，此方法可被任何继承它的类替代：

```c#
public virtual double Area()
{
    return x * y;
}
//示例
class Class1
    {
        public string name { get; set; }
        public int Age{ get; set; }
        public int outs { get; set;}
    //添加-虚方法(Virtual)
        public virtual void show() {
            Console.WriteLine("姓名：{0}\n年龄：{1}\n出生年：{2}",name, Age,outs);
        }
    }
class son_Class2:Class1
    {
        public int math {get; set;}
        public int english { get; set;}
        //重写show方法
    	//重写后再次调用时就调用的重写的方法
        public override void  show()
        {
            Console.WriteLine("姓名：{0}\n年龄：{1}\n出生年：{2}\n数学：{3}\n英语：{4}", name, Age, outs,math,english);
        }
    }

```

##### 隐藏方法



```c#
class Class1
    {
        public string name { get; set; }

        public int Age{ get; set; }
        
        public int outs { get; set;}
        public void show() {
            Console.WriteLine("姓名：{0}\n年龄：{1}\n出生年：{2}",name, Age,outs);
        }
    }
//派生类：继承基类
 class son_Class2:Class1
    {
        public int math {get; set;}
        public int english { get; set;}
        //重写show方法--在基类中的函数不需要加任何关键字，派生类中使用new关键字隐藏基类中的方法
        public new void show()
        {
            Console.WriteLine("姓名：{0}\n年龄：{1}\n出生年：{2}\n数学：{3}\n英语：{4}", name, Age, outs,math,english);
        }
    }
```



#### 抽象类

通过在类定义前面放置关键字 `abstract`，可以将类声明为抽象类。抽象类只有函数的定义，没有函数体。

抽象类不能实例化。 抽象类的用途是提供一个可供多个派生类共享的通用基类定义。 例如，类库可以定义一个抽象类，将其用作多个类库函数的参数，并要求使用该库的程序员通过创建派生类来提供自己的类实现。

```c#
// compile with: -target:library
public class D
{
    public virtual void DoWork(int i)
    {
        // Original implementation.
    }
}

public abstract class E : D
{
    public abstract override void DoWork(int i);
}

public class F : E
{
    public override void DoWork(int i)
    {
        // New implementation.
    }
}
```

#### 密封类、密封方法

通过在类定义前面放置关键字 `sealed`，可以将类声明为[密封类](https://learn.microsoft.com/zh-cn/dotnet/csharp/language-reference/keywords/sealed)。

```c#
public sealed class D
{
    // Class members here.
}
```

密封类不能用作基类。 因此，它也不能是抽象类。 密封类禁止派生。 由于密封类从不用作基类，所以有些运行时优化可以略微提高密封类成员的调用速度。

在对基类的虚成员进行重写的派生类上，方法、索引器、属性或事件可以将该成员声明为密封成员。 在用于以后的派生类时，这将取消成员的虚效果。 方法是在类成员声明中将 `sealed` 关键字置于 [override](https://learn.microsoft.com/zh-cn/dotnet/csharp/language-reference/keywords/override) 关键字前面。 

```c#
public class D : C
{
    public sealed override void DoWork() { }
}
```

密封类不能被继承，密封方法不能被重写。
密封类不能被继承，密封方法不能被重写。

### 访问修饰符

所有类型和类型成员都具有可访问性级别。 该级别可以控制是否可以从你的程序集或其他程序集中的其他代码中使用它们。 [程序集](https://learn.microsoft.com/zh-cn/dotnet/standard/glossary#assembly)是通过在单个编译中编译一个或多个 .cs 文件而创建的 .dll 或 .exe。 可以使用以下访问修饰符在进行声明时指定类型或成员的可访问性：

- [public](https://learn.microsoft.com/zh-cn/dotnet/csharp/language-reference/keywords/public)：同一程序集中的任何其他代码或引用该程序集的其他程序集都可以访问该类型或成员。 某一类型的公共成员的可访问性水平由该类型本身的可访问性级别控制。
- [private](https://learn.microsoft.com/zh-cn/dotnet/csharp/language-reference/keywords/private)：只有同一 `class` 或 `struct` 中的代码可以访问该类型或成员。
- [protected](https://learn.microsoft.com/zh-cn/dotnet/csharp/language-reference/keywords/protected)：只有同一 `class` 或者从该 `class` 派生的 `class` 中的代码可以访问该类型或成员。
- [internal](https://learn.microsoft.com/zh-cn/dotnet/csharp/language-reference/keywords/internal)：同一程序集中的任何代码都可以访问该类型或成员，但其他程序集中的代码不可以。 换句话说，`internal` 类型或成员可以从属于同一编译的代码中访问。
- [protected internal](https://learn.microsoft.com/zh-cn/dotnet/csharp/language-reference/keywords/protected-internal)：该类型或成员可由对其进行声明的程序集或另一程序集中的派生 `class` 中的任何代码访问。
- [private protected](https://learn.microsoft.com/zh-cn/dotnet/csharp/language-reference/keywords/private-protected)：该类型或成员可以通过从 `class` 派生的类型访问，这些类型在其包含程序集中进行声明。

![image-20240201183403675](./imgs/image-20240201183403675.png)

其他修饰符

- 
- static-静态
  在一个类中，如果某个属性用static修饰，则该属性可以被实例化对象共享，而普通属性则不可以
   `static` 修饰符可用于声明 `static` 类。 在类、接口和结构中，可以将 `static` 修饰符添加到字段、方法、属性、运算符、事件和构造函数。
  static修饰的内容不是存储在某个对象中，而是存储在静态存储区中的。

### 接口

接口类似于类，接口使用

接口中只有方法的定义，没有具体的方法体

```c#
//接口定义
public interface Ijiekou
{
    //方法体
    public void mains();
}
//接口实现
public class jiekou : Ijiekou
{
    public void mains()
    {
        Console.WriteLine("这是一个接口实现方法");
    }
}
```

#### 接口继承

与类不同一个类可以继承多个接口

```c#
public interface Ijiekou
{
    //方法体
    public void mains();
}
public interface Ijicheng : Ijiekou
{
    public void jicheng();
    
}
//继承多个接口
//接口定义
public interface Ijiekou
{
    //方法体
    public void mains();
}
public interface Ijicheng
{
    public void jicheng();
    
}

//接口实现
public interface Ijiekou
{
    //方法体
    public void mains();
}
public interface Ijicheng
{
    public void jicheng();
    
}
public class jiekou2 : Ijiekou, Ijicheng
{
    public void mains()
    {
        Console.WriteLine("这是一个接口实现方法");
    }
    public void jicheng()
    {
        Console.WriteLine("这是第二个继承接口");
    }
}
```

### 索引器

参考官方文档

### 运算符重载

参考官方文档

### 泛型

例如，计算两个数的和时，两个类除了数据类型外，其他基本相同，如果再写一遍较为麻烦，所以可以使用泛型。

```c#
 class add<T>
    {

        public T a;



        public add(T a)
        {
            this.a = a;
        }
        public T GetValue()
        {
            
            //执行语句
            return a;
        }
        

    }
     class mains
    {
        static void Main() { 
            add<int> n1 = new add<int>(1);
            Console.WriteLine(n1.GetValue());
            add<double> n2 = new add<double>(1.23);
            Console.WriteLine(n2.GetValue());
        }
    }
```

## 高级篇（暂未更新，以下为学习资料）

【C#编程-第四季-高级篇-宇宙最简单2022最新版】 https://www.bilibili.com/video/BV1mb4y1q78H/?p=2&share_source=copy_web&vd_source=ea0cf64e8dac6f0193a7e28187a0fccb

## 





 
