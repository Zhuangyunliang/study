<center>Java第一天</center>
---



##### 1. 计算机基础

```
电脑的组成：
	CPU 内存 主板 显卡 硬盘 电源等
对于程序员：
	CPU 内存
	计算机最小单元
作为开发者需要考虑的是：
	CPU使用率
	内存的占有率
提升电脑速度：
	换ssd
	加内存
使用电脑建议：
	安装软件不要安装到C盘
	软件安装到自己可以找到的位置
	软件安装路径不要出现中文
```

##### 2. 计算机操作

###### 2.1 操作方式

```
a)图形化界面
	对于普通用户是用方便便捷，但是对于电脑来说浪费了其他资源，不能让电脑处理程序效率变高
	
b)命令行
	对于普通用户，是非常不友好的！操作不方便，命令很麻烦
	但是对于电脑资源使用时极高的，对于开发者操作效率也是非常高！！！
	
DOS命令 了解，做一些基本操作
Linux命令【重点】
	ls cd md rd rm cp chmod kill
```

###### 2.2 DOS命令

```
首先打开命令提示符
	windows + R 弹出运行 输入 cmd
命令学习：
	1. dir
		查看当前【工作目录】中的所有子文件和子文件夹
		【工作目录】
			当前cmd命令提示符，操作命令之前的路径
			如果文件之前带有<DIR>标记代表这是一个文件夹
			文件名称前的数字代表该文件所占的字节数
	2. cd 【重点】
		切换当前工作路径
		路径问题:
			相对路径
				例子：我在1204A办公室，参照物是当前教师
			绝对路径
				例子：我在山东省济南市长清区大学科技园1204A办公室
			展示目录中.和..的问题
				.表示当前【工作目录】
				..表示当前【工作目录】的父目录/上级目录
			后期学习的后台知识和IO流使用
	3. mkdir
		创建文件夹
		可以同时创建多个文件夹，每个文件夹的名字使用空格键隔开
	4. rd 【慎用】
		【注意】
			1. 删除文件夹是直接抹除数据，而不是存到回收站
			2. 不能删除非空文件夹文件【文件删除机制 删除文件夹时从最内层文件进行删除】
	5. echo 【了解】
		使用 echo 123>1.txt
			将123写入到1.txt文件中
		文件后缀名：
			.txt .jpg .gif .exe .png .mp4 .rmvb .avi .mkv .doc .ppt .java .html
			.class .css .js .php .py .c .m .h .md .jsp .mp3 .dll 等
	6. del 【慎用】
		删除文件
		【注意】
		 	1. 删除文件，直接删除，不暂存在回收站
		 	2. 删除文件，必须文件后缀名，删除文件是文件名.后缀名的完整格式
	7. *
		通配符！！注意！！代表所有！！
	8. 方向键上下
		回顾之前操作的命令
	9. exit
		退出
		如果涉及到MySQL操作，一定要使用exit，不然可能导致mysql崩溃
	10. cls
		清理屏幕
	11. 切换盘符
		盘符对应的字母 + 冒号
		D：
		使用图形界面打开文件夹，在地址栏上输入cmd可以直接进入到当前文件路径的cmd界面
		
		
		
```

 

##### 3.  Java介绍

```
Java之父 詹姆斯·高斯林
Java母公司 Sun

Java程序运行都依赖于jvm
一处编译，到处执行
```

##### 4. JDK安装

###### 4.1获取JDK安装包

```
建议，所有的开发有关的软件都要从官网获取！
JDK 1.8 官网下载地址
	https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html
本电脑安装路径D:\Program Files\Java
安装建议：
	1.不安装在C盘
	2.安装路径不要带有任何的中文
	3.jdk和jre安装在同目录下
	
```

######  4.2 安装

```
安装可以不再安装JRE，也就是安装过程的第二步
```

###### 4.3 JDK环境变量的配置

```
JDK环境配置

Windows + E  --> 此电脑 --->

	新建系统变量
		变量名： JAVA_HONE
		变量值：找打自己的jdk安装路径
			例如：D:\Program Files\Java\jdk1.8.0_231
		
	新建系统变量
		变量名： CLASS_PATH
		变量值：.;%JAVA_HOME%\lib;%JAVA_HOME%\lib\tools.jar
			前边.;开头，前边没有空格
		
	编辑Path变量
		变量名： Path
		变量值：在末尾添加   ;%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;		
```

##### 5. JDK目录结构解释

###### 6.1 JDK和JRE

```
JDK Java Development Kits Java开发工具集
	JDK == JRE + Java开发工具
JRE Java Runtime Environment Java运行环境
	JRE == JVM + 支持JVM运行的核心类库
```



![](C:\Users\lenovo_zhuang\Desktop\学习笔记MD\java_zhuang\javase\img\jdk目录结构.png)

###### 6.2 JDK的目录结构

bin:

​	Binary  二进制目录，在bin目录结构下保存的内容都是Java工具集

​	javac.exe

​	java.exe

​	javadoc.exe

​	javap.exe

include:

​	java程序运行需要使用系统资源的接口文档。 C语言实现

jre:

​	Java Runtime Enviroment

lib:

​	Library 库 核心类库 支持jvm运行的内容

src.zip:

​	Java源代码

##### 6. Java第一行代码准备

###### 6.1 Notepad++

```
Notepad++ 菜单栏 ——> 首选项 ——> 自动完成
						 ——> 新建 【编码设置为ANSI 终端无法识别utf-8】
```

###### 6.2 Java代码

```java
// 这里是完成的第一个代码
// 代码名称是 HelloWorld.java
class HelloWorld{
    public static void main(String[] args){
        System.out.println("Hello World");
    }
}
```

###### 6.3 编译执行代码

```
使用javac.exe编译Java代码
格式：
	javac HelloWorld.java
	生成一个对应的.class文件，该文件叫字节码文件
	
使用java.exe执行Java程序，也就是.class字节码文件
格式：
	java HelloWorld
	执行结果
```

###### 6.4第一行代码出现的问题

```
1.手速太慢，1分钟200 APM
2.拼写错误！
	大小写 中英文符号
3.迷路！代码文件混乱。
4.代码格式不规范！
5.操作不熟练！
```



