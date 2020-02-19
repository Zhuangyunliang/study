<center><h2>IDEA安装使用，方法总结和数组</h2></center>
##### 1. IDEA安装

###### 1.1 IDEA获取

```
从官方网站获取：
	https://www.jetbrains.com/idea/download/#section=windows
	下载 Ultimate版本
```

###### 1.2 安装

```
Create Desktop Shortcut:
	根据电脑系统的位数选择
其他选项尽量不要选择
安装路径不允许使用中文
```

###### 1.3 配置

![](C:\Users\lenovo_zhuang\Desktop\学习笔记MD\java_zhuang\javase\img\font配置.png)

![](C:\Users\lenovo_zhuang\Desktop\学习笔记MD\java_zhuang\javase\img\自动补齐快捷键.png)

```
1. 可以取消Swing 和 Android 插件
2. 主题看自己！！
```



##### 2.创建第一个IDEA项目

```

```

##### 3. 关于方法的总结

###### 3.1 方法名

```
1. 见名知意，动宾结构
2. 方法调用是需要通过方法名来完成的，在方法名之后有一个小括号，这是方法和变量的区别
3. 严格小驼峰命名法
```

###### 3.2 形式参数列表

```
1. 考虑什么时候用的上形式参数列表!!!
	方法的执行需要外部数据
2. 考虑形式参数类别是什么类型!!!
	int 1 char '1' 数据类型一致化！！！
3. 需要的形式参数列表可以有多个数据，需要使用逗号隔开。
	例如：
		(int num1, double num2, float num3; char ch);
	调用方法时要求数据类型一一对应
		(10, 3.14, 5.5F, 'A'); √
		('a', 5.5F, 4.5, 2000000); ×
```

###### 3.3 返回值类型

```
1. 是该方法对外的反馈！！！
	Sout不是最终处理数据的方式！！！
2. 是否需要返回值
	根据实际业务来考虑
3. 数据类型
	boolean
	整型，浮点型，char型
	对象类型 【最常用】
4. 数据含义
	数据
	判断
	状态
	情况
	... ...
```

##### 4. 数组【重点】

###### 4.1 为什么需要使用数组

```
在开发中会出现大量除服的，并且是统一类型的数据，需要同时时候，如果按照一个一个的变量定义，会导致代码出现以下一些问题:
	1. 代码过于臃肿
	2. 代码阅读性极差
	3. 代码维护性极差
```

###### 4.2 生活中的数组案例

```
图书馆
	非常完美的归纳总结思想
	图书馆的藏书会有很多本，书籍会对应有大类
	推荐<<Java核心技术 卷1/卷2>>
	加入图书馆有10本
	这些书会放在同一个书架上

细节: 
	1. 保存位置相同， 同一个书架
	2. 有一个统一的对外编号
	3. 每一本书有一个独立的编号，方便管理
```

##### 4.3 Java中定义数组的格式

```
变量定义的格式：
	数据类型 变量名 = 初始化数据;
数组的定义格式：
	数据类型[] 数组名 = new 数组类型[容量];
	
赋值号左侧：
	数据类型:
		确定当前数组中保存的数据类型是什么，要求当前数据中有且只能保存的指定数据类型，严格执行数据类型一		致化
	[]:
		1. 确定当前创建的是一个数组类型
		2. 确定数组名是一个【引用数据类型】，引用数据类型的变量保存的是另一个数据空间的地址
	数组名：
		1. 操作当前数组使用的名字
		2. 数组名是一个引用数据类型变量
赋值号右侧：
	new：
		"创建数据空间的关键字"
	数据类型：
		前后一致，保证数据类型一致化，要求创建的数据类型是指定的数据类型。
	[容量]：
		确定当前数组中数据容量是多少，而且创建之后，不可改变！！
```

###### 4.4 数组的使用

```java
在图书编号的末尾会存在一个唯一标识！！！

数组的下标：
	数据的有效下标是用 0 开始到 数组的容量 - 1
	如果数组的容量是10，有效下标的范围就是 0 ~ 9
使用格式：
	数组名[有效下标];
	arr[0] = 10;
	System.out.println(arr[0]);
	
演示代码：
public class MethodTest {
    public static void main(String[] args) {
        // 定义一个int类型的数组
        // 数据类型 [] 数组名 = new 数据类型[]

        // 这里创建一个可以保存10个int类型数据的数组，数组名是 arr
        int[] arr = new int[10];

        // 给予数组中下标为0的元素赋值
        arr[0] = 10;

        // 给予数组中下标为5的元素赋值
        arr[5] = 20;

        // 展示数组中下标为 0 和下标为 5 数据保存的值
        System.out.println(arr[0]);
        System.out.println(arr[5]);

        // 给予下标为10的元素赋值
        // arr[10] = 30;  10超出元素的表示范围,出现数组下标越界异常
    }
}
```

##### 4.5 数组的内存分析图【重点】

```
内存是分区域的！！！
	栈区 堆区 数据区 代码区
```

![](C:\Users\lenovo_zhuang\Desktop\学习笔记MD\java_zhuang\javase\img\数组内存图.png)

```
0x8848 这是内存地址！！！
就认为这是山东省泰安市岱岳区浪潮科技园C区10楼

数组下标 arr[0] arr[5]
就认为这里找的是房间号 1001A 1006A

1. 数组的容量不能为0
2. 数组名是一个引用数据类型，其中保存的内存地址不能为null
```

###### 4.6 数组和循环之间不得不说的秘密

```java
对于数组的CRUD操作都是依赖于循环完成的，而且大部分使用的循环都是for循环！！
因为for循环可以通过第一行的循环语句得知当前循环的大概次数，这个特征非常适用于数组！！！
案例代码：
	public class Demo {
    public static void main(String[] args) {
        int[] arr = new int[10];

        for (int i = 0; i < arr.length; i++) {
            arr[i] = i + 1;
        }
        System.out.println(Arrays.toString(arr));
    }
}
```

###### 4.7 数组作为方法的参数[【重点】

```java
// main方法就是使用数组作为形式参数列表的方法
 public static void main(String[] args) {
 	
}
// String[] args 就是数组作为方法参数的格式
// 数据类型[] 形式参数的名字
/*
需求：
	完成一个方法，给予int类型数组进行赋值操作
	方法名：
		assignIntArray
	形式参数列表：
		需要一个int类型数组，格式 int[] arr
	返回值类型：
		void 这里目前不考虑返回值类型
*/

/*
需求：
	完成一个方法，展示int类型数组
	方法名：
		printIntArray
	形式参数列表：
		需要展示的int类型数组，格式 int[] arr
	返回值类型：
		void 这里目前不考虑返回值类型，后期可能会考虑 boolean int
*/

public class Demo {
    public static void main(String[] args) {
        // 定义一个int类型数组，容量为10,
        int[] arr = new int[10];

        /*
         该方法需要一个参数是一个数组类型
         把数组名作为方法的参数传入
        */
        assignIntArray(arr);

        printIntArray(arr);
    }

    /**
     * 完成一个方法，给予int类型数组进行赋值操作
     * @param arr int类型数组
     */
    public static void assignIntArray(int[] arr) {
        for (int i = 0; i < arr.length; i++) {
            arr[i] = i + 1;
        }
    }

    /**
     * 展示一个int类型数组
     * @param arr 需要int类型数组
     */
    public static void printIntArray(int[] arr) {
        for (int i = 0; i < arr.length; i++) {
            System.out.println(arr[i]);
        }
    }
} 
```



##### 【常用KeyMap】

|        快捷键        |              功能              |
| :------------------: | :----------------------------: |
|     Alt + Insert     |            新建一切            |
|         psvm         |          main方法快速          |
|       Ctrl + z       |              撤销              |
|   Shift + Ctrl + z   |             反撤销             |
|       Ctrl + c       |            复制一行            |
|  Ctrl + X/Ctrl + Y   |            删除一行            |
|    Ctrl + Alt + L    |       对齐代码(和QQ冲突)       |
|       Alt + /        |            补齐代码            |
| Shift + Ctrl + Space |            智能补齐            |
|     Alt + Enter      |            修复代码            |
| Ctrl + Shift + Enter |          自动补齐分号          |
|    Ctrl + Alt + V    |   可以生成一个方法对应的变量   |
|       Ctrl + Q       | 可以快速查看对应代码的文档注释 |
|                      |                                |

