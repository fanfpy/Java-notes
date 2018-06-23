# 基本数据类型

类型 | 缺省值|  长度 | 范围 
---|---|---|---
byte | 0|8位 | -128~127
short | 0|16位 | -32768~32767 
int | 0|32位| -3147484648~2147843647 
long | 0|64位 | ... 
float | 0.0|32位 | ... 
double |0.0 |64位 | ... 
boolean | false|1位 | false，true

### 常量池

```
Integer x = new Integer(123);
Integer y = new Integer(123);
System.out.println(x == y);    // false
Integer z = Integer.valueOf(123);
Integer k = Integer.valueOf(123);
System.out.println(z == k);   // true
```

##### new Integer(123)每次都会创建新的对象 Integer.valueOf会使用常量池已有的对象

```
String s1 = "123";
String s2 = "123";
String s3 = new String("123");
System.out.println(s1 == s2); //true
System.out.println(s1 == s3);  //false
```
##### 当两个 String的拥有相同的两个值时，他们会引用常量池相同的地址，来节省空间

### == 和equals()的区别

	对于基本类型，== 判断两个值是否相等，基本类型没有 equals() 方法。
	对于引用类型，== 判断两个实例是否引用同一个对象，而 equals() 判断引用的对象是否等价。

### 参数传递 

Java 的参数是以值传递的形式传入方法中，而不是引用传递。

# 流程控制

- [if](#if)
- [switch](#switch)
- [while](#while)
- [for](#for)
- [continue](#continue)
- [break](#break) 




# 数组

### 数组是一个固定长度的，包含了相同类型数据的 容器

```
    int[] a = new int[10];
```

### 冒泡排序

```
class Hello {
    public static void main (String[] args){
        int [] array = new int []{32,43,2,2,11,52};
		for (int i=0 ; i<array.length ; i++) {
			for(int j=0; j<array.length-i-1 ;j++){
				if(array[j]>array[j+1]){
					int t=array[j+1];
					array[j+1]=array[j];
					array[j]=t;
				}
			}
		} 
		
		for(int a:array){
			System.out.println(a);
		}
	}
}
```

## Arrays工具类

### 常用方法
- Arrays.toString(array) //转换为字符串
- Arrays.sort(array) //排序 	
- Arrays.binarySearch(array,num) //搜索  必须先排序才能查找 
- Arrays.copyOfRange(array,start,end) //数组复制数组复制


# 面向对象 

- [继承](#extend)
- [封装](#)
- [多态](#duotai)
- [接口](#interface)
- [抽象类](#abstract)
- [重载](#Overload)
- [重写](#Override)
 
<span id="extend">1.继承</span>

	在同一包下 private类不能被继承 不同包下 private和package(默认修饰符)不能被继承

<spann id = "duotai">3.多态</span>

	一个类的多种实现 实现多态的方法(接口 抽象类 继承 重载)

<span id="interface">4.接口</span>

	接口的成员（字段 + 方法）默认都是 public 的，并且不允许定义为 private 或者 protected。

<span id="abstract ">5.抽象类</span>

	抽象类和抽象方法都使用 abstract 进行声明。抽象类一般会包含抽象方法，抽象方法一定位于抽象类中。既有已经实现的类 又有为实现的类 需要子类继承之后去实现

<span id ="Overload">6.重载</span>

	存在于同一个类中，指一个方法与已经存在的方法名称上相同，但是参数类型、个数、顺序至少有一个不同。应该注意的是，返回值不同，其它都相同不算是重载。

<span id="Override">7.重写</span>

	存在于继承中，指子类实现了一个与父类在方法声明上完全相同的一个方法；不同的实现

# 集合框架（用的最多的几个）
- Collection
	- List(线性存储)
		- [ArrayList](#arrayist)
		- [LinkedList](#inkedlist)
	- Set
		- [HashSet](#hashset)
- Map
	- Map
		- [HashMap](#hashmap)


<span id="arraylist">ArrayList</span>	

	ArrayList是顺序结构，所以定位很快，指哪找哪。 就像电影院位置一样，有了电影票，一下就找到位置了,但插入，删除数据慢

<span id="linkedlist">LinkedList</span>

	LinkedList 是链表结构，就像手里的一串佛珠，要找出第99个佛珠，必须得一个一个的数过去，所以定位慢，但应为是链表结构，插入，删除数据快

<span id="hashset">HashSet</span>

	无序 不重复

<span id="hashmap">HashMap</span>

	HashMap储存数据的方式是—— 键值对,键不能重复，值可以重复 ,查找速度极快
