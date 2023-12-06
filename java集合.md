# java集合

#### 集合和数组的区别

 ![这里写图片描述](https://img-blog.csdn.net/20180803193134355?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZlaXlhbmFmZmVjdGlvbg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70) 

#### Collection集合的方法:

 ![这里写图片描述](https://img-blog.csdn.net/20180803193423722?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZlaXlhbmFmZmVjdGlvbg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70) 

常用的集合分类:

Collection接口的接口 对象的集合(单列集合)

- List接口:元素按进入先后有序保存，可重复
  - ListedList接口实现类，链表，插入删除，没有同步，线程不安全
  - ArrayList接口实现类,数组，随机访问，没有同步，线程不安全
  - Vector接口实现类 数组，同步，线程安全

- Set接口:仅接受一次，不可重复，并做内部排序
  - Hashset使用hash表(数组)存储元素
  - TreeSet底层实现为二叉树，元素排好序

Map接口 键值对的集合(双列集合)

- Hashtable接口实现类，同步，线程安全

- HashMap接口实现类，没有同步，线程不安全

- TreeMap红黑树队所以的key进行排序

  

#### List和set集合详解

list和set的区别

- 有序性
  - List保证按插入顺序排序
  - Set存储和取出顺序不一致

- 唯一性
  - List可以重复
  - Set元素唯一

- 获取元素
  - List可以通过索引直接操作元素
  - Set不能根据索引获取元素

**List**：

1. ArrayList：底层数据结构是数组，查询快，增删慢，线程不安全，效率高，可以存储重复元素
2. LinkedList 底层数据结构是链表，查询慢，增删快，线程不安全，效率高，可以存储重复元素
3. Vector:底层数据结构是数组，查询快，增删慢，线程安全，效率低，可以存储重复元素
   

 ![这里写图片描述](https://img-blog.csdn.net/20180803201736883?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZlaXlhbmFmZmVjdGlvbg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70) 

#### ArrayList的使用方法

```java
import java.util.ArrayList;  // 引入 ArrayList 类
public class Test{
	public static void main(String[] args){
	//初始化
		ArrayList<String> list=new ArrayList<String>();
		//添加元素
		list.add("xieshizhang");
        list.add("malong");
        list.add("zhangsan");
        list.add("cuixu");
        //删除元素
        list.remove(1);//括号中为索引 成功删除malong
       //计算大小size()方法
        System.out.println(list.size());
        //add(int index,E element)在指定地方添加元素
        list.add(2,"很长的一段文字");
        //替换集合中的元素
        list.set(0,"xieshizhang1");
        //使用循环来打印集合
        for(int i=0;i<list.size();i++){
            System.out.println(list.get(i));
        }
	}
}
```

#### Arraylist排序

Collections类也是一个非常有用的类,位于java.util包下,提供的sort()方法可以对字符或数字列表进行排序

```java
import com.sun.xml.internal.ws.policy.privateutil.PolicyUtils;

import java.util.Collections;
import java.util.ArrayList;
public class Test {
    public static void main(String[] args) {
        ArrayList<String> list=new ArrayList<String>();
        list.add("KBC");
        list.add("DWQ");
        list.add("ZWE");
        list.add("PWE");
        //调用Collections类中的sort方法
        Collections.sort(list);
       for (int i=0;i<list.size();i++){
           System.out.print(“ ”+list.get(i));
       }
    }
}
//输出结果为 DWQ KBC PWE ZWE
```

#### HashSet

1. HashSet是基于HashMap来实现的，实现了Set接口，同时还实现了序列化和可克隆化。而集合（Set）是不允许重复值的。

2. 所以HashSet是一个没有重复元素的集合，但不保证集合的迭代顺序，所以随着时间元素的顺序可能会改变。( 输出元素的出现顺序是不确定的，并不会自动排序。 )

3. 由于HashSet是基于HashMap来实现的，所以允许空值，不是线程安全的。
4.  HashSet是基于HashMap实现的，区别就在于在HashMap中输入一个键值对，而在HashSet中只输入一个值。 

```java
import java.util.HashSet;
import java.util.Iterator;
public class Test{
	public static void main(String[] args){
		HashSet<String> list=new HashSet<String>();
        list.add("abc");
        list.add("bcd");
        list.add("abd");
        //删除元素
        list.remove("abc");
        System.out.println("list");
        //判断集合中是否存在该元素
        boolean con=list.contains("acc");
        System.out.println(con);//输出false
        //判断集合是否为空
        boolean con1=list.isEmpty();
        System.out.println("con1");//输出false
        //元素的个数
        System.out.println(list.size());
        //遍历HashSet
        for(String s:list1){
            System.out.println(s);
        }
        //使用迭代器
        Iterator<String> iterator=list.iterator();
        while(iterator.hasNext()){
            Integer element=inerator.next();
            System.out.println(element);
        }
	}
}
```

其他一些常见方法



- - | Modifier and Type | Method and Description                                       |
    | :---------------: | ------------------------------------------------------------ |
    |     `boolean`     | `add(E e)`  将指定的元素添加到此集合（如果尚未存在）。       |
    |      `void`       | `clear()`  从此集合中删除所有元素。                          |
    |     `Object`      | `clone()`  返回此 `HashSet`实例的浅层副本：元素本身不被克隆。 |
    |     `boolean`     | `contains(Object o)`  如果此集合包含指定的元素，则返回 `true` 。 |
    |     `boolean`     | `isEmpty()`  如果此集合不包含元素，则返回 `true` 。          |
    |    `Iterator`     | `iterator()`  返回此集合中元素的迭代器。                     |
    |     `boolean`     | `remove(Object o)`  如果存在，则从该集合中删除指定的元素。   |
    |       `int`       | `size()`  返回此集合中的元素数（其基数）。                   |
    |   `Spliterator`   | `spliterator()`  在此集合中的元素上创建*[late-binding](Spliterator.html#binding)*和*故障快速* [`Spliterator`](../../java/util/Spliterator.html) 。 |

#### HashMap

 在HashMap中允许相同的值（value）存在的，但是不允许相同的键（key）存在。 

```java
import java.util.HashMap;//调用HashMap
import java.util.Iterator;

public class Test001 {
    public static void main(String[] args) {
        HashMap<Integer,String> map=new HashMap<>();

        // 添加键值对
        map.put(1, "apple");
        map.put(2, "banana");
        map.put(3, "apple"); // 不同的键可以对应相同的值
        //删除元素
        map.remove(1);
        //清除集合中的所有元素
        //map.clear();
        //集合是否为空
        boolean con=map.isEmpty();
        //System.out.println(con);
        //遍历集合
       for (Integer key:map.keySet()){
           String value= map.get(key);
           System.out.println("键为"+key+"键值为"+value);
       }
        //通过迭代器遍历
        Inerator<Map.Entry<Integer,String> it=map.entry()Set.inerator();
        while(it.hasNext()){
             Map.Entry<Integer,String> entry=it.next();
               System.out.println(entry);
        }
    }
    }
}
```

