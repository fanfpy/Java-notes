# Java基础

### 基本数据类型


类型 | 缺省值|  长度 | 范围 
---|---|---|---
byte | 0|8位 | -128~127
short | 0|16位 | -32768~32767 
int | 0|32位| -3147484648~2147843647 
long | 0|64位 | ... 
float | 0.0|32位 | ... 
double |0.0 |64位 | ... 
boolean | false|1位 | false，true


## 流程控制

### if 
### switch
### while
### for
### continue
### break 


## 数组

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