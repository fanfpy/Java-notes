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
System.out.println(s1 == s3);  //false 地址不同
System.out.println(s1.equals(s3));//true  equals做内容判断 
```
##### 当两个 String的拥有相同的两个值时，他们会引用常量池相同的地址，来节省空间

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

