# JAVA期末复习笔记

#### Java基础部分

**标识符**:用来标识类名，对象名，变量名，方法名，类型名，数组名，文件名的有效字符序列

**合法的标识符**：

- 由字母，数字，下划线_,美元符号$和￥组成，并且首字母不能是数字

- 不能把Java关键字和保留字作为标识符

- 标识符对对大小写敏感

  关键字:java中已赋予了特定含义的

   ![在这里插入图片描述](https://img-blog.csdnimg.cn/2021071710543467.png) 

 **保留字：** `const、goto`，Java版本中尚未使用，但以后版本可能会作为关键字使用 

 **变量：程序运行期间可以被改变的量。在程序中使用变量，必须先创建它并为它取一个名字，并且指明它能够存储信息的类型，这称为“变量声明”，也叫容器的创建。** 

**变量的使用：**

- 变量的声明：数据类型 变量名;
- 变量的赋值：变量名 = 数据;
- 变量的操作：放入打印语句进行输出或者进行运算

**Java 中的注释有三种：**

- 单行注释
- 多行注释
- 文档注释

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210717105952514.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0x6eTQxMDk5Mg==,size_16,color_FFFFFF,t_70) 

 **基本数据类型（8个），也称原始数据类型：** 

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210717105845105.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0x6eTQxMDk5Mg==,size_16,color_FFFFFF,t_70) 

 **引用数据类型（3种）：数组、类、接口** 

**类型转换：**

- 自动类型转换，也叫隐式转换;隐式转换 通常发生在容量较小的数据类型向容量较大的数据类型转换时，或者当某些数据类型与其他数据类型进行运算时。 

- 强制类型转换，也叫显式转换; 通过强制转换运算符将一种数据类型转换为另一种数据类型。显式类型转换需要明确地指定要转换的数据类型，并且可能会导致数据精度的丢失或溢出。 

- ```java
  short s=888;
  long l=s;//自动类型转换
  System.out.println(l);
  
  char ch='A';
  int num=ch;//char转换成int
  布尔型数据没有隐式转换，因为它只能能表示true或false两个值
  //强制类型转换
      int i=12;
  	byte b=(byte) i;//强制转换
  
  char ch='a';
  byte a=(byte) ch;
  
  ```

  **运算符**

  **运算符：一种特殊符号，用以表示数据的运算、赋值和比较数与整数**

  **运算符分类：算术运算符、赋值运算符、比较运算符、逻辑运算符、三元运算符**

1. #### 算法运算符

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210717110447464.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0x6eTQxMDk5Mg==,size_16,color_FFFFFF,t_70) 

2.赋值运算符

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210717110501938.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0x6eTQxMDk5Mg==,size_16,color_FFFFFF,t_70) 

1. 首先，将变量`a`的当前值3除以变量`b`的当前值2，计算得到商1和余数1。
2. 将余数1赋值给变量`a`，即`a = 1`。

3.比较运算符

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210717110513439.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0x6eTQxMDk5Mg==,size_16,color_FFFFFF,t_70) 

4.逻辑运算符

- &(与)-------->见false则为false;只要其中一个运算结果为false则结果也为false
- |(或)---------->见true则为true; 只要其中一个运算结果为true则结果则为true。 
- ^(异或)------>相同则为false，不同为true； 结果都为true或者结果都为false,则打印的最后结果为false。结果一个为true，一个为false,则最后打印的结果为true。 
- ！(非)----->取反 例如

```java
int a=10;
int b=20;
System.out.println(a<b);//输出true
System.out.println(!(a<b));输出false
```

- &&(短路与)------->见false则为false,如果左边的表达式为true,右边的表达式会继续运算。如果左边的表达式为false,右边的表达式不会继续运算

```java
int a=10;
int b=20;
System.out.println(a++>30&&b++>30);//flase
System.out.println(a);//输出11
System.out.println(b);还是输出20，后面的b++并不会执行
```

- ||(短路或)---------->见true则为true, 如果左边的表达式为true,右边的表达式不会继续运算。如果左边的表达式为flase.则会算出右边的表达式

```java
int a=10;
int b=20;
System.out.println(a++<30&&b++>30);//true
System.out.println(a);//输出11
System.out.println(b);还是输出20，后面的b++并不会执行
```

5.三元运算符

条件表达式:b?x:y;先计算条件b，然后进行判断，如果b的值为true，计算x的值，运算,运算结果为x的值；否则，计算y的值，运算结果为y；

```java
int num=2>3?2+2:4+4;
System.out.println(num);//8
```

#### Java流程控制语句

##### 选择结构

**if语句**：if(条件表达式){一条或者多条语句};

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210717111408712.png) 

 **if else语句：** `if(条件表达式) {语句块1} else {语句块2}` 

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210717111608985.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0x6eTQxMDk5Mg==,size_16,color_FFFFFF,t_70) 

if多分支语句:

```java
if(条件表达式1){
	语句块1
}else if(条件表达式2){
	语句块2
}else if(条件表达式3){
	语句块3
}else{
	语句块4
}
```

switch开关语句:

```java
switch (expression) {
    case value1:
        // 当expression等于value1时执行的代码块
        break;
    case value2:
        // 当expression等于value2时执行的代码块
        break;
    case value3:
        // 当expression等于value3时执行的代码块
        break;
    // 可以有更多的case语句
    default:
        // 当expression与上述所有值都不匹配时执行的代码块
        break;
}
```

```java
import java.util.Scanner;
 
public class SwitchDemo2 {
    public static void main(String[] args) {
        //创建键盘录入对象
        Scanner sc = new Scanner(System.in);
 
        System.out.println("请输入一个数据（1-7）");
        int number = sc.nextInt();
 
        switch (number) {
            case 1:
                System.out.println("星期一");
                break;
            case 2:
                System.out.println("星期二");
                break;
            case 3:
                System.out.println("星期三");
                break;
            case 4:
                System.out.println("星期四");
                break;
            case 5:
                System.out.println("星期五");
                break;
            case 6:
                System.out.println("星期六");
                break;
            case 7:
                System.out.println("星期日");
                break;
            default:
                System.out.println("输入的数据有误");
                break;
        }
    }
}
```

##### 循环结构

在程序中当要做重复性的做某项工作时可以使用循环语句，包括for循环，while循环，do...while循环。

```java
for循环语句:
for(初始化表达式;条件表达式;迭代语句){
	循环体语句
}
增强for循环语句:
遍历集合
        for(集合元素的类型  局部变量  :  集合对象)
    内部代码仍然调用迭代器
    for(Object obj : coll){
        System.out.println(obj);
    }
遍历数组
        for(数组元素的类型  局部变量  :  数组对象)
    for (int i : arr){
        System.out.println(i);
    }
while循环语句:
while(条件表达式){
		语句或语句块
}
do....while循环语句:
do{
	语句或语句块
}while(条件表达式);
```

##### 流程跳转

流程跳转语句:break;continue

- break：在switch中结束case条件判断，在循环体中结束循环
- continue：作用在循环体中，结束循环体的本次循环，而进入下次循环

##### 数组

数组声明的三种方式:

- 数据类型[] 数组名=new 数据类型[长度];
- 数据类型[] 数组名={数据,...数据....,数据};
- 数据类型[] 数组名=new 数据类型长度[] {数据,数据,....数据};

```java
int[] arr=new int[5];等同于int arr[]=new int[5];
int[] arr={1,2,3,4,5};等同于int arr[]={1,2,3,4,5};推荐第二种
int[] arr=new int[]{1,2,3,4,5};
int arr[]=new int[]{1,2,3,4,5};
```

####  类的定义以及使用重载

```java
[修饰符] class 类名{//类的声明部分
	[成员变量]
	[成员方法]
}
```

成员变量的声明:

```
[修饰符] 数据类型 变量名;
```

成员方法的声明:

```
[修饰符] 返回值类型 方法名([数据类型 参数名,……]){
	//方法体，该方法完成的功能代码
}
```

构造器的声明:

```
[修饰符] 构造器名([数据类型 参数名,……]){
  //构造器完成的功能代码
}
```

注意:

 **注意：**
①构造器名必须和类名一致
②构造器没有返回值类型
③任何类都含有构造器。如果没有显式地定义类的构造器，
④则系统会为该类提供一个默认的无参的构造器。一旦在类中显式地定义了构造器，系统就不会再为这个类提供默认的构造器了。 

##### 类的使用

类变量的声明:

```java
类名 对象名=new 构造器[参数列表]
例如
public class Cat {
    public static void main(String[] args) {
        Person person=new Person("xieshizhang",18);带参构造器
        Person person1=new Person();无参构造器
        person.name="xieshizhang";
        person.age=18;
        System.out.println(person.name);
        System.out.println(person.age);
    }
}
class Person{
    public String name;
    public int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public Person(){
    }
}
```

```java
class Cat{
	public static void main(String[] args){
		Person person1=new Person();
        person.setName("xieshizhang");
        person.setAge(18);
        System.out.println(person.getName());
        System.out.println(person.getAge());
	}
}
class Person{
     public String name;
     public int age;
    public void setName(String name){
        this.name=name;
    }
    public void setAge(int age){
        this.age=age
    }
    public String getName(){
        return getName;
    }
    public int getAge(){
        return getAge;
    }
}
```

主要区别：

- 带参构造方法在创建对象时直接对属性进行赋值，而setter方法是在对象创建后通过方法调用来设置属性值。
- 带参构造方法适用于在创建对象时一次性设置属性值，而setter方法可以在对象创建后灵活地修改属性值。
- setter和getter方法可以提供更多的灵活性和控制来管理属性的访问，例如对属性进行验证或添加其他逻辑。

##### 方法的重载

一个类中定义了多个方法名相同而参数不同的方法

重载在同一个类中，方法名相同，参数不同（参数的个数、顺序、类型不同）

```java
class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public double add(double a, double b) {
        return a + b;
    }
}
```

注意:一个类中的带参构造和不带参构造也算是重载

##### 方法的返回值类型

- 无返回值类型:void,return;//结束方法体(无返回值类型的方法可以省略return语句)

- 返回值类型:数据类型(基础数据类型,引用数据类型),return 数据;//结束方法体;并返回一条数据

  ```java
  public class Cat {
      public static void main(String[] args) {
          Cat cat=new Cat();
          System.out.println(cat.num());
      }
      public int num(){
          int num1=40;
          return num1;
      }
  
  }
  ```

  

#### 关键字

##### **this**关键字

this是一种特殊的引用，指向当前对象。

this的两种使用方法:

如果发生局部变量和成员变量命名冲突时，可以通过this.成员变量名的方式来区分成员变量和局部变量

成员变量:义在类中的变量，它属于整个类并且在类中可以被任何方法访问。成员变量在创建对象时会被初始化，并在整个对象存活期间一直存在。因此，成员变量的作用范围是整个类，而不是仅限于某个方法或代码块。例如：

```java
public class Student{
	public String name;//成员变量
	public static void main(String[] args){
	
	}
}
```

局部变量:是定义在方法、代码块或构造函数中的变量，它们只在声明它们的代码块中生效。局部变量的生命周期只存在于代码块中，代码块结束后，局部变量就会被销毁。通常情况下，局部变量需要在使用前进行初始化。例如：

```java
public class Student{
	publice Student(){
		 String name;//局部变量
	}
}
```

```java
public class Test(){
    int i=20;//成员变量
    public static void main(String[] args){
        Test test=new Test();
        test.TestThis();
    }
    public void TestThis(){
        int i=30;//局部变量
        //成员变量和局部变量同名，成员变量被隐藏
        System.out.println(i); //输出30
        //通过this关键字访问成员变量
        System.out.println(this.i); //输出20
    }
}
```

 **一个构造方法中需要调用本类的另一个构造方法，可以通过this()的方式调用，但this()必须要书写在第一行。** 

```java
public class Person {
    private String name;
    private int age;

    // 第一个构造方法
    public Person() {
        this("Unknown", 0); // 调用带参构造方法
    }

    // 第二个构造方法
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    // 测试代码
    public static void main(String[] args) {
        Person person1 = new Person(); // 调用第一个构造方法
        System.out.println(person1.getName()); // 输出：Unknown

        Person person2 = new Person("Tom", 20); // 调用第二个构造方法
        System.out.println(person2.getName()); // 输出：Tom
        System.out.println(person2.getAge()); // 输出：20
    }
}

```

 **static关键字：** 

静态变量： 使用static修饰的成员变量叫做静态变量，静态变量和非静态变量的区别是：静态变量被所有的对象所共享，在内存中只有一个副本，它当且仅当在类初次加载时会被初始化。而非静态变量是对象所拥有的，在创建对象的时候被初始化，存在多个副本，各个对象拥有的副本互不影响。static成员变量的初始化顺序按照定义的顺序进行初始化。

静态方法： 使用static修饰的成员方法叫做静态方法，静态方法可以不依赖于任何对象进行访问（对于静态方法来说，是没有this的），由于这个特性，在静态方法中不能访问类的非静态成员变量和非静态成员方法，因为非静态成员方法/变量都是必须依赖具体的对象才能够被调用。

```java
调用格式：类名.静态变量名 ，类名.静态方法名()
```

##### 静态内部类

static 修饰类的话只能修饰内部类： 静态内部类与非静态内部类之间存在一个最大的区别: 非静态内部类在编译完成之后会隐含地保存着一个引用，该引用是指向创建它的外围类，但是静态内部类却没有。没有这个引用就意味着：1. 它的创建是不需要依赖外围类的创建。2. 它不能使用任何外围类的非 static 成员变量和方法。

静态内部类创建对象的方法:

格式: `外部类名.内部类名 对象名 = new 外部类名.内部类构造器;`

例子: `Outer.Inner in = new Outer.Inner();`

```java
//内部类
public class Person{
	class Student{
	}
}
//静态内部类
public class Outer{
	//静态成员内部类
	public static class Inner{
	}
	public static void main(String[] argd){
		//实例化Inner
		Outer.Inner in=new Outer.Inner();
	}
}
```

 在内部类Inner下可以和外部类一样, 可以定义变量和方法 

```java
//内部类
public class Person{
	 public static class Student{
         //实例成员变量
         private String name;
         //静态成员变量
         public static int age;
	}
    public static void main(String[] args){
        Person.Student student=new Person.Sutdent();
        student.name="xieshizhang";
        //静态成员变量的访问,可以直接用类名
        Student.age=18;//student.age=18;
    } 
}

```

-  静态内部类中可以**直接**访问**外部类的静态成员** 

- 静态内部类不可以直接访问外部类的实例成员

##### 成员内部类

什么是成员内部类？

无static修饰，属于外部类的对象。

JDK16之前，成员内部类中不能定义静态成员，JDK 16开始也可以定义静态成员了

成员内部类的格式:

```java
public class Outer{
	//成员内部类
	public class Inner{
	}
}
```

成员内部类创建对象的方法:

成员内部类是属于外部类的实例对象的, 因此需要先new外部类(), 得到外部类实例后再外部类实例.new 内部类

格式: 外部类名.内部类名 对象名 = new 外部类构造器().new 内部类构造器();

范例: Outer.Inner in = new Outer().new Inner();

```java
public class Outer{
	public class Inner{
	}
	public static class main(String[] agrs){
		Out.Inner inner=new Outer().new Inner();
	}
}
```

- 成员内部类可以直接访问外部类的静态成员
- 成员内部类的实例方法可以直接访问外部类的实例成员

```java
public class Person{
	public String name;
    static int age;
	public class Student{
		void Test(){
            	//z直接访问外部类的静态成员
			System.out.println(age);
            //实例方法直接访问外部类的实例成员
            System.out.println(name);
           
        }
	}
}
```

##### 静态代码块

是一个以static为前导的代码块，一般用于为类的工作做一些初始化工作，如初始化一些静态变量。一个类中可以有许多静态初始化块，并且它们可以出现在类体的任何地方。运行时系统会保证静态初始化块会按照它们在源代码中出现的顺序被调用

static块可以用来优化程序性能：因为它只会在类加载的时候执行一次

```java
public class Test {
    int i;
    static String name;
    static int num;
    static int age;
    static {
        num=20;
        name="xieshizhang";
        age=21;
    }
    public static void main(String[] args) {
    }
```

##### spuer关键字

super关键字代表的是父类对象

 **使用方式：**
`super.属性名、super.方法名();`用于在子类中调用父类被隐藏的同名实例变量
`super([参数列表])`用于在子类的构造方法中调用父类的构造方法 

 每一个子类的构造方法在没有显示调用super()系统都会提供一个默认的super()，super()必须是构造器的第一条语句 

```java
public class TestThis extends Test{
    //访问父类的属性
        int age=super.age;
	//重写父类的方法
    @Override
    public void method() {
        super.method();
    }
		//调用父类的构造方法
    public TestThis() {
        super(name,age);
    }

    public static void main(String[] args) {
     TestThis testThis=new TestThis();
        System.out.println(testThis.age);
        System.out.println(testThis.name);
       testThis.method();
    }
}
//
public class Test {
    public String name;
    public int age;

    public Test(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void method(){
        System.out.println("父类的方法");
    }
}
```

#####  **final关键字:** 

final 关键字，意思是最终的、不可修改的，最见不得变化 ，用来修饰类、方法和变量，具有以下特点：

修饰类：类不能继承，final 类中的所有成员方法都会被隐式的指定为 final 方法；
修饰符变量：该变量为常量，，如果是基本数据类型的变量，则其数值一旦在初始化之后便不能更改；如果是引用类型的变量，则在对其初始化之后便不能让其指向另一个对象。
修饰符方法：方法不能重写
说明：使用 final 方法的原因有两个。第一个原因是把方法锁定，以防任何继承类修改它的含义；第二个原因是效率。在早期的 Java 实现版本中，会将 final 方法转为内嵌调用。但是如果方法过于庞大，可能看不到内嵌调用带来的任何性能提升（现在的 Java 版本已经不需要使用 final 方法进行这些优化了）。类中所有的 private 方法都隐式地指定为 final。

```java
//用于变量
public class Example{
	public static final int age=100;//其他程序不能修改age的值
}
//用于方法
public class Parent{
	public final void display(){
		System.out.println("该方法不能被父类重写");
	}
}
//用于类
public final class FinalClass{
    //这个类不能被继承
}
```

#### java的三大特性

##### 封装

**封装指隐藏对象的状态信息（属性），不允许外部对象直接访问对象的内部信息（private实现）。但是可以提供一些可以被外界访问的方法来操作属性。**

**将类中成员变量private，提供public的get和set方法来控制属性的存取动作，以保证对私有属性操作的安全性：**

```java
public class User {
    private String name;
    private int age;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
    private void eat(){
        //将方法设置私有达到封装目的
        System.out.println("吃东西");
    }
}
```

##### 继承

 继承extends：多个类中存在相同属性和行为时，将这些内容抽取到单独一个类中，那么多个类无需再定义这些属性和行为，只要继承单独的那个类即可。多个类可以称为子类，单独这个类称为父类或者超类。 

```java
[修饰符] class 子类名 extends 父类名{
   类体部分
}
```

继承是使用已存在的类的定义作为基础建立新类的技术，新类的定义可以增加新的属性或方法（对父类进行扩展），也可以拥有父类的属性和方法，并且通过自己的方法再次实现父类的方法（重写）。通过使用继承，可以快速地创建新的类，可以提高代码的重用，程序的可维护性，节省大量创建新类的时间 ，提高我们的开发效率。

```java
public class Person {
    public int  age;
    public String sex;
    public void eat(){
        System.out.println("吃饭");
    }
    public void sleep(){
        System.out.println("睡觉");
    }

}
//
public class Student extends Person{
        public String name;

    public Student(int age, String sex) {
        super(age, sex);
    }

    public void qita(){
            System.out.println("其他");
        }



    public static void main(String[] args) {
        Student student=new Student();
        student.name="xieshizhang";
        student.age=18;
        student.sex="男";
        student.eat();
    }
}
```

Java只支持单继承，不支持多继承。一个类只能有一个父类，不可以有多个父类，Java支持多层继承(继承体系),Java继承了父类非私有的成员变量和成员方法，但是请注意:子类无法继承父类的构造方法。

 **注意：不要仅为了获取其他类中某个功能而去继承 ，类与类之间要有所属(“is a” )关系** 

**方法的重写**

子类从父类继承的某个实例方法无法满足子类的功能需要时，需要在子类中对该实例方法进行重新实现，这样的过程称为重写，也叫做覆写、覆盖。

方法重写的前提：继承，子类的修饰符大于等于父类，方法名、参数列表、返回值类型必须相同

##### 多态

多态:一种事务的多种形态(多态的前提:继承，重写，向上转型)

多态存在的三个必要条件

1. 继承或实现：在多态中必须存在有继承或实现关系的子类和父类
2. 方法的重写：子类对父类中的某些方法进行重新定义（重写，使用@Override注解进行重写）
3. 基类引用指向派生类对象，即父类引用指向子类对象，父类类型：指子类对象继承的父类类型，或实现的父接口类型

多态的格式

- 父类类型 变量名 = new 子类类型（）；

- 然后通过 **变量名.方法名（）**调用在子类中重写的方法

- ***\*多态体现为父类引用变量可以指向子类对象：\**定义了一个父类类型的引用，指向新建的子类类型的对象，由于子类是继承他的父类的，所以父类类型的引用是可以指向子类类型的对象的**

  - **多态成员变量：编译运行看左边**

    此处举例的Person为父类,Student是子类

    Person student=new Student;//Person是引用类型，Student是实际类型

    Ststem.out.println(student.age);student的引用类型是Person,所以取到父类Person中的值，说白了就是student属于Person类，Person中的变量的值是多少就通过对象就取得多少。

```java
public class Person{
	int age=11;
}
public class Student extends Person{
	int age=33;
	public static void main(String[] args){
		Person student=new Student;
		Ststem.out.println(student.age);//输出结果为11
	}
}
```

- **多态成员方法：编译看左边，运行看右边**
- Animal dog = new Dog（）； //**Animal是引用类型，Dog是实际类型**
- dog.eat();   //**变量dog的实际类型是Dog,即是由Dog 这个实际类型new出来的，因此dog.eat() 调用的应该是子类Dog中重写的方法**

```java
//父类
public class Animal{
	public void eat(){
		System.out.println("午餐")
	}
}
//子类Dog
//子类
public class Dog extends Animal {
    
    @Override
    public void eat() {
        System.out.println("晚餐");
    }
}
//启动项
public class DemoApplication {
    public static void main(String[] args) {
        //父类类型 对象 = new 子类类型（）
        Animal dog = new Dog();
        dog.eat();//输出晚餐
    }
}
```

**多态的特点**

1. 多态情况下，子类和父类存在同名的成员变量时，访问的时父类的成员变量
2. 多态情况下，子父类存在同名的非静态成员方法时，访问的是子类中重写的方法
3. 多态情况下，子父类存在同名的静态成员变量成员方法时，访问的是父类的成员函数
4. 多态情况下，不能访问子类独有的方法

对于子类独有的方法，父类无法访问，

**父类Animal保持不变：**

```java
//父类
public class Animal{
	public void eat(){
		System.out.println("午餐吃狗粮")
	}
}
//子类Dog；增加子类独有的方法walk()
//子类
public class Dog extends Animal {
 
    
    public void walk(){
        System.out.println("子类独有的方法");
    } 
    @Override
    public void eat() {
        System.out.println("晚餐吃狗粮");
    }
}
//启动项
//根据多态成员方法中编译看左边，运行看右边的原理
//Animal  dog  =  new Dog（）；
//可知 左边的Animal引用类型中没有walk()这个方法，故编译不通过，编译爆红
public class DemoApplication{
	public static void main(String[] agrs){
		Animal dog=new Dog();
		dog.eat;////访问的是子类中重写的方法
		dog.walk;//walk方法爆红,即编译报错，编译看左边，dog类的实例对象Animal没有walk（）这个方法，所以编译报错
	}
}
```

如果想要访问子类独有的方法，可以用引用类型转换

**引用类型转换**

为什么需要引用类型转换

- 上面的例子说明了，在多态情况下，使用Animal引用类型构建出来的对象dog无法访问子类Dog所独有的方法walk（）；强行调用时方法会爆红，编译出错，即我们所说的**编译看左边，运行看右边**

- 而且我们在多态情况下调用方法时，首先会检查等式左边的引用类型（父类）中是否有该方法存在，如果父类中没有该方法，则编译器直接报错，也就代表着，父类无法调用子类独有的方法

- 既然编译都出错了，更别说运行了，这也是多态所造成的，因此如果我们想要调用子类的方法，必须做到向下转型

  **向上转型**(自动转换)

 先了解什么向上转型（儿子变父亲） 

 ![img](https://img-blog.csdnimg.cn/44494e3c6313491680a5a73278c3f9bf.png) 

 多态本身是子类向父类向上转换（自动转换）的过程，这个过程是默许的，当父类引用指向一个子类对象时，就是向上转型 

```java
父类引用指向子类对象
Animal dog=new Dog();
左边的Animal是引用类型，而dog是由右边的Dog实例对象new出来的，在上面这个等式中，左边的引用Animal指向了子类的对象dog，原本是子类对象的dog完成了向上转型
```

**向下转型**

 ![img](https://img-blog.csdnimg.cn/6eae988781a04bd2a6b5af3de8c9a446.png) 

 向下转型是父类向子类转换的过程，这个过程需要强制转换（父亲变儿子肯定是需要条件的），一个可以将父类对象转换为子类对象，可以使用强制类型转换的格式，这便是向下转型 

 **对于Dog、Cat这些子类来说，他们只是父类Animal的一部分，而对于父类来说。他拥有更多的子类 牛、羊等**，**所以一旦父类要转换成子类，就必须指定要变成哪个子类，必须有指向性，所以向下转型才是强制转换** 

使用格式:

```java
向上转型
父类类型  变量名  = new 子类类型（）；
Animal dog = new  Dog（）
向下转型
子类类型 子类变量名 = （子类类型） 父类变量名
Dog dog1 = (Dog) dog;
```

```java
//父类
public class Animal{
	public void eat{
		System.out.println("吃午饭")
	}
}
//子类
public class Dog extends Animal {
    public void walk(){
        System.out.println("子类独有的方法");
    }
    @Override
    public void eat() {
        System.out.println("晚餐吃狗粮");
    }
}
//启动项
public class DemoApplication{
	public static void main(String[] agrs){
	//向上转型
	Animal dog=new Dog();
	向下转型
	Dog dog1=(Dog) dog;
	dog.eat();//输出晚餐吃狗粮
	dog1.walk();//输出子类特有的方法
	}
}
//所以对于多态中，无法使用子类特有的方法也通过向下转型，将父类类型强制转换为某个子类类型后，再进行方法的调用
```

**向下转型的问题**

虽然可以通过向下转型可以调用子类独有的方法，但也会产生下面的问题

增加一个子类Cat类，

Cat类中有其独有的方法sleep（）

```java
 //Cat类通过extends关键字继承父类Animal
public class Cat extends Animal {
    public void sleep(){
        System.out.println("Cat类独有的方法");
    }
    @Override
    public void eat() {
        System.out.println("晚餐吃猫粮");
    }
}
//父类Animal
public class Animal {
    public void eat() {
        System.out.println("午餐吃狗粮");
    }
}
//子类Dog
public class Dog extends Animal{
    	public void walk(){
           System.out.println("Dog类独有的方法");
        }
    @Override
    public void eat(){
        System.out.println("晚餐吃狗粮")
    }
}
//启动项
public class DemoApplication{
    public static void main(Stirng[] args){
        //向上转型
        Animal cat=new Cat();
        向下转型
        Dog dog1=(Dog) cat;  
        dog1.walk();//报错
    }
}
```

 **控制台打印输出：爆出异常**ClassCastException，即类型转换异常 

分析：为什么会爆出类型转换异常

因为 在启动项中，向上转型的过程，Animal cat = new Cat(); cat对象是由子类Cat构造出来的
而向下转型的过程中 Dog dog1 = (Dog) cat; 却将其变成了Dog 类的对象，
Dog类和Cat类都是Animal类的儿子类 ，
上面的步骤中的第二步将子类Cat的对象cat变成了兄弟类的对象dog,这就不是向下转型了，因此会报类型转换异常

##### Instanceojf关键字详解

 java为我们提供了一个关键字instanceof,它可以帮助我们避免出现ClassCastException这样的异常， 

格式:

```java
变量名 instanceof 数据类型
```

解释：

- 如果变量属于该数据类型或者其子类型，返回true
- 如果变量不属于该数据类或者其子类型，返回false

 直接拿启动项来进行说明， 

```
public class DemoApplication{
	public static void main(String[] args){
	向上转型
	Animal cat =new Cat();
	if(cat instanceof Cat){
		Cat cat1=(Cat) cat;
		cat1.sleep();
	}else if(cat instanceof Dog){
		Dog dog=(Dog) cat;
		dog.walk();
	}
	}
}
```

#### 接口中的链式调用

```java
public interface Car(){
	Car color();
	Car type();
} 
public class CarImpl implements Cat{
	public Car color(){
		System.out.println("颜色");
		return new CarImpl;//或者return this
	}
	public Car type(){
		System.out.println("类型");
		return null;
	}
	public static void main(String[] args){
		CarImpl imp=new CarImpl();
		Car car=imp.color().type();//链式访问
		
	}
}
```

