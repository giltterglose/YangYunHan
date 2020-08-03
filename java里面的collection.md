# Java里面的collection/Map

我们在曾经的代码里面看过ArrayList，List等代码，其实这些代码是用来收集类对象，可以直接取用这些类来进行首先我们得了解API架构。

## 1. 泛型相关

### 1.1 基本概念

泛型代表可以是任意的 Java 对象，比如 String、Course 等。泛型如果要使用，还需要在方法名前面再额外声明，比如我们这里的<<T>T>

声明泛型类这么干：

```Java
public class Example<T>{
    public static List<T> ele;
    public void method(T t){
        
    }
    public T get(){
        return (T) ele[index];
    }
}
```

案例里面我们使用了泛型的语法。实际上，里面的T可以换成任意大写字母，因为你不知道你要输入何种类型的对象，所以泛型可以解决这一问题，就像C++里面的模板。

上述get方法，必须传入一个T类型的数据，否则直接报错。

实际上T可以代表任意的传入对象数据类型，但是一旦确定必须是那个类型，否则就报错。

实际上，有很多接口是支持泛型的，支持泛型的接口可以使接口兼容更多对象数组。

泛型方法：

```java
public static <T> T method(T[] objs,int index){
    return objs[index];
}
```

此时，任意类型的T都可以传入这里。

### 1.2 自定义泛型

## 2. Collection架构

collection架构定义在java.util.Collection里面，

它是除`Map`外所有其他集合类的根接口。Java的`java.util`包主要提供了以下三种类型的集合：

- `List`：一种有序列表的集合，例如，按索引排列的`Student`的`List`；
- `Set`：一种保证没有重复元素的集合，例如，所有无重复名称的`Student`的`Set`；
- `Map`：一种通过键值（key-value）查找的映射表集合，例如，根据`Student`的`name`查找对应`Student`的`Map`。

我们先一个个讨论相关接口。

### 2.1 List接口

list是ArrayList的接口，我们如果打开它的API，可以发现有很多接口。

我们可以存储集合：

```java
List<String> strings = new ArrayList<>();
```

List是一个collection，作用就是收集对象，并以索引的方式保留收集的对象顺序，操作之一是java.util.ArrayList，我们通过这个ArrayList方法就可以来实现这个接口。

```
// 这里的 Java 对象类型可以是任意的对象类型
// 比如 String、Integer、House 等
// 这里的 <> 是 Java 泛型的规范,记住这个语法就行了
```

ArrayList 本质上就是一个动态数组对象，可以方便的存储集合对象，一般来说我们会把同一个类型的数据存储在这个 ArrayList 里。我们如果要使用 ArrayList 就必须要先实例化，实例化的语法都是一样的，使用 new 关键字，并且需要指定对象类型。

可以用ArrayList实例化，也可以用List实例化。

```java
ArrayList<String> arr = new ArrayList<>();
```

注意一下，ArrayList 这个对象是存放在 java.util包下面的，所以如果要使用它就需要先进行 import 完整的引入是

import java.util.ArrayList.

包括List, import java.util.List 顺带说一下，如果不想导入那么多包，可以java.util.* 代替，就包括了util包下面全部，但是不建议这么做，很容易犯错。

add方法：

我们来看一个例子：

```java
import java.util.ArrayList;

public class ArrayListTest1{

  public static void main(String[] args){

    // 创建一个 ArrayList 存储字符串集合
    ArrayList<String> strs = new ArrayList<>();

    // 添加数据到 ArrayList 实例里
    strs.add("张三");
    strs.add("李四");

  }

}
```

add方法可以用来添加东西在集合里面，完成数据添加。

get/size方法。

动态数组具有数组特点：

可以获取长度size()

可以根据索引来取出数组里面具体的值get(index)，索引和数组一样都是从零开始。

我们看一个案例：

```java
import java.util.ArrayList;

public class ArrayListTest1{

  public static void main(String[] args){

    // 创建一个 ArrayList 存储字符串集合
    ArrayList<String> strs = new ArrayList<>();

    // 添加数据到 ArrayList 实例里
    strs.add("张三");
    strs.add("李四");

    // 获取集合的长度
    int size = strs.size();

    // 使用 for 循环迭代每一条记录
    for(int i=0;i<size;i++){
       // 根据索引获取值，值的类型是 String
       String str = strs.get(i);
       System.out.println(str);
    }

  }

}

```

我们上述的for循环可以改成增强for循环：

```java
import java.util.ArrayList;

public class ArrayListTest1{

  public static void main(String[] args){

    // 创建一个 ArrayList 存储字符串集合
    ArrayList<String> strs = new ArrayList<>();

    // 添加数据到 ArrayList 实例里
    strs.add("张三");
    strs.add("李四");

    // 获取集合的长度
    int size = strs.size();

    // 使用 for 循环迭代每一条记录
    for(String str : strs){
       System.out.println(str);
    }

  }

}
```

注意观看：

```java
ArrayList<String> strs = new ArrayList<>();
for(String str : strs){
  System.out.println(str);
}
```

语法结构：

```java
for( 集合变量的类型 变量名称 : 集合变量 )
```

这种写法可以看前面我们说的增强for循环里面看看

增强for循环相当于一个迭代器，可以对数组里面的元素进行一一迭代。

方法等价于：

```java
for(int i=0;i<size;i++){
    // 根据索引获取值，值的类型是 String
    String str = strs.get(i);
    System.out.println(str);
 }
```

所以list遍历和arraylist一模一样

### 2.2 Map接口

map接口相当于键值对，是map映射导致的


Map（映射）是遵循 key:value 这样的形式的集合。key、value 的类型可以是任何的 Java 对象。

我们大部分的情况下，都会使用 HashMap 这个 Map 的实现类。所以如果想得到一个 Map 的实例的话可以使用 HashMap

```java
import java.util.Map;
import java.util.HashMap;

// key value 得是 Java 类型
Map<key,value> map = new HashMap<>();
```

不同的是map里面使用的方法是map.put(key,value)来完成数据存储。

由于 Map 的键和值都是 Java 对象类型，所以我们在实际创建的时候也需要指定对应的类型，上面的案例中 key 是数字类型：Integer，value 是字符串类型:String，所以我们可以用Map<Integer,String>来用，者也是泛型的使用。

看一个案例：

```java
// 实例化Map对象
Map<Integer,String> map = new HashMap<>();

map.put(1,"Monday");
map.put(2,"Tuesday");
map.put(3,"Wednesday");
map.put(4,"Thursday");
map.put(5,"Friday");
map.put(6,"Saturday");
map.put(7,"Sunday");
```

如果我们要知道某一个值，就采用map.get(key)来实现

```java
String weekText = map.get(3);
System.out.println(weekText);
```

结果是：Wednesday

map存储键值对真的很方便。

要打印集合，size方法依然实用。测定集合大小。也可以循环遍历：for

```java
int size = map.size();
System.out.println(size);
```

结果是 7

map遍历相对麻烦，因为是key:value的形式，所以我们一般先得到这个数据格式的集合（entrySet），完整的例子如下：

```java
for (Map.Entry<Integer,String> entry:map.entrySet()){
    System.out.println("Key = " + entry.getKey() + 
                  ", Value = " + entry.getValue());
}
```

但是会发生输出顺序不一样的情况，我们后面可以采用LinkedList和TreeMap来进行代替。

```java
List<T> list = new LinkedList<>();
Map<T1,T2> map = new TreeMap<>();
```

这样就可以保证正常顺序输出了。

至于map相关方法，可以看看这个文档。

https://www.youkeda.com/post/detail/a6d92e04c0e4479faf913c8d53098e27

### 2.3 Set接口

我们会发现在生活里面难免会有输入重复的东西，为了抹去，我们可以采用Set（集合）方法进行，Set接口有一个常用类：HashSet

```java
public class Main {
    public static void main(String[] args) {
        Set<String> set = new HashSet<>();
        System.out.println(set.add("abc")); // true
        System.out.println(set.add("xyz")); // true
        System.out.println(set.add("xyz")); // false，添加失败，因为元素已存在
        System.out.println(set.contains("xyz")); // true，元素存在
        System.out.println(set.contains("XYZ")); // false，元素不存在
        System.out.println(set.remove("hello")); // false，删除失败，因为元素不存在
        System.out.println(set.size()); // 2，一共两个元素
    }
}

```

我们可以看看HashSet核心代码：

```java
public class HashSet<E> implements Set<E> {
    // 持有一个HashMap:
    private HashMap<E, Object> map = new HashMap<>();

    // 放入HashMap的value:
    private static final Object PRESENT = new Object();

    public boolean add(E e) {
        return map.put(e, PRESENT) == null;
    }

    public boolean contains(Object o) {
        return map.containsKey(o);
    }

    public boolean remove(Object o) {
        return map.remove(o) == PRESENT;
    }
}
```

add方法是保证有没有加入成功并且没有重复。

可以用来统计不重复单词的方法。

但是你会发现HashSet并不是有序的，我们可以换成TreeSet方法进行。

- `HashSet`是无序的，因为它实现了`Set`接口，并没有实现`SortedSet`接口；
- `TreeSet`是有序的，因为它实现了`SortedSet`接口。

和treemap类似

实际上就是判断hashcode是否一模一样。

### 2.4 Queue接口

数据结构里面队列的原理就像排队一样底部出尾巴进。我们queue接口也是一模一样的原理，有很多方法add，remove等等方法，queue有自己的方法offer、poll和peek方法。区别在于前者会抛出异常，后者是返回布尔类型的值。

offer是在队列后面添加对象，成功为true，失败是false

poll方法是取出队列前端对象，队列为空返回null

peek是取得但是不取出前端对象，队列为空返回null

queue接口我们可以用LinkedList来进行实例化

```java
Queue queue = new LinkedList();
```

### 2.5 集合的操作

删除函数remove()

集合既然可以添加也可以删除，如果我们要移除某一个元素

List.remove(int index)

看一个案例：

```java
import java.util.*;

public class ListRemoveDemo {
    public static void main(String args[]) {

        List<String> list = new ArrayList<>();

        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("10");
        list.add("20");

        System.out.println("集合: " + list);

        // 删除第4条记录
        list.remove(3);

        System.out.println("修改后的集合: " + list);
    }
}
```

我们移除了10

结果是：

集合: [Geeks, for, Geeks, 10, 20]
修改后的集合: [Geeks, for, Geeks, 20]

合并addAll()

当我们遇到两个集合，想合并为一个集合的时候，就可以使用addAll方法

```java
import java.util.*;

public class ListAddAllDemo {
    public static void main(String args[]) {

        List<String> list1 = new ArrayList<>();
        list1.add("Geeks");
        list1.add("For");
        list1.add("ForGeeks");


        System.out.println("ArrayList 1: "
                           + list1);

        List<String> list2 = new ArrayList<>();

        list2.add("GeeksForGeeks");
        list2.add("A computer portal");

        System.out.println("ArrayList 2: "
                           + list2);

        // 合并 list2 到 list1 集合中
        list1.addAll(list2);

        System.out.println("Joined ArrayLists: "
                           + list1);
    }
}
```

结果如下：

ArrayList 1: [Geeks, For, ForGeeks]
ArrayList 2: [GeeksForGeeks, A computer portal]
Joined ArrayLists: [Geeks, For, ForGeeks, GeeksForGeeks, A computer portal]

截取subList()

有的时候，我们会想从集合里截取一段内容，我们就得需要subList(int begin,int end)方法。

```java
import java.util.*;

public class SubListDemo {
    public static void main(String args[]) {

        List<String> list = new ArrayList<>();

        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("10");
        list.add("20");

        System.out.println("集合: " + list);

        List<String> arrlist2 = list.subList(2, 4);

        System.out.println("修改后的集合: " + arrlist2);
    }
}
```

结果是：修改后的集合: [Geeks, 10]

就会发现返回不包含结束索引，即：包含begin但是不包含end

## 3. 其他操作

### 3.1 List和数组的互换

大家就会发现 List 和数组的功能是很类似的，但是 List 的能力会更强而且它是动态的空间，而数组每次使用都是必须要先确定数组大小。

由于各种各样的情况，我们不可避免的出现数组和 List 共存的情况，这个时候就需要我们进行数据的互转。

我们在java里面提供了一个包：java.util.Arrays包，用来专门处理集合与数组的关系。

Arrays 是一个工具类，所以它的方法都是静态方法，我们先了解最常用的转化方法

1.static List asList(T… a)

asList 方法是把任意的相同对象实例转变为 List。T在上面就强调过是泛型了。

我们看一个案例：

```java
import java.util.Arrays;
import java.util.List;

public class ArraysMain {
  public static void main(String[] args) {
    // 数字数组
    Integer[] intArr = { 10, 20, 15, 22, 35 };
    // 转化数组为 list
    List<Integer> lists = Arrays.asList(intArr);
    System.out.println("集合的长度是: " + lists.size());
  }
}
```

注意：Arrays.asList() 的参数值必须是对象数组，才支持泛型，就是参数值必须是对象数组。

对象数组：必须使用对象数据类型来定义的才叫对象数组。相当于基本数据类型把首字母大写就可以了，但是int必须是Integer,char必须是Character才行。

也就是说，对于基本类型（小写的 byte,short,int,long,float,double,boolean）的数组，包含了什么是不清楚的，所以不要使用Arrays.asList来转换基本类型数组。

案例：

```java
import java.util.Arrays;
import java.util.List;

public class ArraysMain {
 public static void main(String[] args) {
   // 转化数组为 list
   List<String> lists = Arrays.asList("小王","小明");
   System.out.println("集合的长度是: " + lists.size());

   // 转化数组为 list2
   List<String> lists2 = Arrays.asList("小王","小明","小李");
   System.out.println("集合2的长度是: " + lists2.size());
 }
}
```

所以在不能确定参数个数的时候尽量采用List方法

所以上面输出结果：

集合的长度是: 2
集合2的长度是: 3

2.List转数组：

List里面有一个toArray()方法。可以把类别转化成数组。

```java
import java.util.List;
import java.util.ArrayList;

public class List2ArrayTest {
    public static void main(String[] args)
    {
        List<Integer> al = new ArrayList<Integer>();
        al.add(10);
        al.add(20);
        al.add(30);
        al.add(40);

        // 转化为数组
       Integer[] arr = al.toArray(new Integer[]{});

        for (Integer x : arr) {
          System.out.println(x + " ");
        }
    }
}
```

3.List 转字符串

List 转字符串也是非常容易的，我们可以使用 String.join("split",list) 方法进行。

具体看看以下代码：

```java
import java.util.*;

public class Array2StringTest {
    public static void main(String args[]) {
        // 创建字符串集合
        List<String> list = Arrays.asList("Geeks", "ForGeeks", "GeeksForGeeks");

        // 转化集合为字符串， 使用 `,` 分割
        String string = String.join(",", list);
        // 打印结果
        System.out.println("字符串是: " + string);
    }
}
```

还可以这么写：

```java
import java.util.*;

public class Array2StringTest {
    public static void main(String args[]) {
        // 字符串数组
        String[] arr = new String[]{"Geeks", "ForGeeks", "GeeksForGeeks"};
        // 创建字符串集合
        List<String> list = Arrays.asList(arr);

        // 转化集合为字符串， 使用 `,` 分割
        String string = String.join(",", list);
        // 打印结果
        System.out.println("字符串是: " + string);
    }
}
```

结果是：

字符串是: Geeks,ForGeeks,GeeksForGeeks

补充介绍一下，这里 import 语句使用了 * 这样就可以把同一个包下的类导入，比如 import java.util.*;，这样 java.util.List、java.util.ArrayList、java.util.Arrays只需要导入一次就可以啦。

### 3.2 排序问题

我们有一堆对象数组需要排序，怎么处理？

方法是用Arrays.sort()

java.util.Arrays 这个工具类非常强大，它的 sort 方法就可以实现数字的排序，默认它的排序是从小到大的顺序排序

我们来看一个例子：

```java
import java.util.Arrays;

public class ArraysSortTest {
    public static void main(String[] args) {

        // Get the Array
        Integer[] intArr = { 10, 20, 15, 22, 35 };

        // To sort the array using normal sort-
        Arrays.sort(intArr);

        System.out.println("Integer Array: "
                           + Arrays.toString(intArr));
    }
}
```

结果是

```
Integer Array: [10, 15, 20, 22, 35]
```

除了 Arrays.sort 方法外，大家注意看到最后一行我们还使用了 Arrays.toString 方法进行打印。

他们的方法签名都被变成字符串，实际上当我们执行 Arrays.toString 方法的时候，Java 执行的是自动遍历每一个数据并调用它的 toString 方法，组合成一个字符串

调用Comparable or Comparator 接口

我们刚才已经了解了，Arrays.sort 默认执行的是从小到大的排序（升序）的规则，如果我们想降序排序呢（从大到小），Arrays 还有一另外一个排序方法：

```java
static <T> void sort(T[] a, Comparator< super T> c):
```

我们重点看第二个参数：我们可以在第二个参数里传递自定义比较类来确定排序，java.util.Comparator是一个接口，用于声明比较规则一般配合排序一起使用，我们看一下这个接口的方法

```Java
public interface Comparator<T> {
  //返回值是 int，我们根据返回值 >0、=0、<0 进行重新排序
  int compare(T o1, T o2);
}
```

如果第一个参数：o1 > 第二个参数：o2则执行的是升序，o1<o2执行的是降序，举个例子：

```java
import java.util.*;

public class ArraysSortTest2 {
    public static void main(String[] args) {

        Integer[] intArr = { 10, 20, 15, 22, 35 };

        // 自定义排序
        Arrays.sort(intArr, new Comparator<Integer>(){
            public int compare(Integer o1, Integer o2){
                // 判断 o2>o1，执行降序排序
                return o2-o1;
            }
        });

        System.out.println("Integer Array: "
                           + Arrays.toString(intArr));
    }
}
```

我们要在compare方法里面加入比较项目来搞，后续我们可能会用lambda表达式处理。

结果是：Integer Array: [35, 22, 20, 15, 10]

我们换以下顺序呢？

```java
Arrays.sort(intArr, new Comparator<Integer>(){
            public int compare(Integer o1, Integer o2){
                // 判断 o1<o2，执行升序排序
                return o1-o2;
            }
        });
```

结果是：Integer Array: [10, 15, 20, 22, 35]

关于集合的排序：我们在学生信息管理系统里面经常使用

数组可以排序，集合同样也可以。我们可以借助另外一个工具类来完成集合的排序，就是 java.util.Collections 这个 Collections 工具类也有个 sort 方法来处理排序。

原型是：static <T> void sort(List<T> list, Comparator<? super T> c)

有一点需要注意的是，如果执行了 Collections.sort 方法，list 的顺序会直接被修改为排序后。

我们可以采用定义的方法进行排序，指定对什么进行排一下

```java
// 实现升序排序
Collections.sort(ar, new Comparator<Student>(){
    public int compare(Student a, Student b) {
    // 第一个参数的学号 > 第二个参数的学号
    return a.getRollNo() - b.getRollNo();
    }
});
```

我们后面有可能会用lambda表达式处理，现在只是提一下。

我们来看一个案例：

```java
import java.util.*;

public class ListSortTest {
  public static void main (String[] args) {
    List<Student> ar = new ArrayList<Student>();
    ar.add(new Student(111, "bbbb", "london"));
    ar.add(new Student(131, "aaaa", "nyc"));
    ar.add(new Student(121, "cccc", "jaipur"));

    System.out.println("原始集合");
    for (int i=0; i<ar.size(); i++) {
      System.out.println(ar.get(i));
    }

    // 实现升序排序
    Collections.sort(ar, new Comparator<Student>(){
      public int compare(Student a, Student b) {
        // 第一个参数的学号 > 第二个参数的学号
        return a.getRollNo() - b.getRollNo();
      }
    });

    System.out.println("\n排序后的集合");
    for (int i=0; i<ar.size(); i++) {
      System.out.println(ar.get(i));
    }

  }
}
```

结果是：

原始集合：
111 bbbb london
131 aaaa nyc
121 cccc jaipur

排序后的集合：
111 bbbb london
121 cccc jaipur
131 aaaa nyc

我们发现按照升序方式排列了，如果排序代码变成以下，就成了：

```java
// 实现降序排序
Collections.sort(ar, new Comparator<Student>(){
    public int compare(Student a, Student b) {
    // 第二个参数的学号 > 第一个参数的学号
    return b.getRollNo() - a.getRollNo();
    }
});
```

这样，collection基本上就差不多了。
