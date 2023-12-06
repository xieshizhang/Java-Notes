# Java抽象类和接口

#### 抽象类

```java
abstract class Person{  //抽象类
     // 抽象类中的方法一般要求都是抽象方法，抽象方法没有方法体
    abstract void eat();
}
```

抽象类在实现多态中的意义

抽象类存在的最大意义就是被继承，当被继承后就可以利用抽象类实现多态

```java
public class Student extends Person {
    @Override
    void eat() {
        System.out.println("吃饭");
    }

    public static void main(String[] args) {
        Person student=new Student();
        student.eat();
    }
}
```

```java
abstract class Person{
      abstract void eat();
}
class Teacher extends Person{

      @Override
      void eat() {
            System.out.println("第一个");
      }
}
class Student extends Person{

      @Override
      void eat() {
            System.out.println("第二个");
      }
}
class Qita extends Person{

      @Override
      void eat() {
            System.out.println("第三个");
      }
}
class DemoApp{
      public static void main(String[] args) {
            Teacher teacher=new Teacher();
            Student student=new Student();
            Qita qita=new Qita();
            Person persons[]={teacher,student,qita};
            for (int i=0;i<persons.length;i++){
                  Person person=persons[i];
                  person.eat();
            }
      }
}
```

注意事项

当一个普通类继承抽象类时，必须重写抽象类的所以方法；

抽象类不能实例化；只能被继承；

抽象类和继承的区别就是:继承不一定要重写所有方法(不重写也可以);

#### 接口

**抽象类是从多个类中抽象出来的模板，如果将这种抽象进行的更彻底，则可以提炼出一种更加特殊的“抽象类”——接口（Interface）🤔。**

📝接口是Java中最重要的概念之一，它可以被理解为一种特殊的类，不同的是接口的成员没有执行体，是由全局常量和公共的抽象方法所组成。

定义一个接口

```java
public interface 接口名{
	int a=10;
	//抽象方法
	public abstract void method1();// public abstract 是固定搭配，可以不写
	void method2();
}
//接口只包含抽象方法；所有也不能直接实例化接口
```

用关键字implements来实现接口

```java
public interface Teacher{
	void work();
}
public class Student implements Teacher{
	void work(){
	System.out.println("工作");
	}
}
```

 **就像普通类实现实现抽象类一样，一个类实现某个接口则必须实现该接口中的抽象方法，否则该类必须被定义为抽象类** 

##### 抽象类和接口的区别

 Java中接口和抽象类的定义语法分别为interface与abstract关键字。 

**相同点**

都不能被实例化， 接口的实现类或抽象类的子类都只有实现了接口或抽象类中的方法后才能实例化。 

**不同点**

1. 抽象类中的抽象方法的修饰符只能为**public**或者protected，默认为**public**；接口中的方法默认使用public修饰

2. 接口成员变量默认为**public static final**，必须赋初值，不能被修改。抽象类中成员变量默认default，可在子类中被重新定义，也可被重新赋值；

3. 实现接口的关键字为implements，继承抽象类的关键字为extends。一个类可以实现多个接口，但一个类只能继承一个抽象类。所以，使用接口可以间接地实现多重继承。

4. 接口强调特定功能的实现，而抽象类强调所属关系。

5. 抽象类可以包含方法、构造方法，方法可以实现，但是构造方法不能用于实例化，主要用途是被子类调用。接口只有定义，不能有方法的实现，java 1.8中可以定义default方法体

   ```java
   public interface Test{
   	default void test2{
   	System.out.println("在接口中实现方法");
   	}
   }
   public class Student implments Test{
   	public static void main(String[] args){
   	//向上转型
   	Test test=new Student();
   	test.test2();
   	}
   }
   ```

   

