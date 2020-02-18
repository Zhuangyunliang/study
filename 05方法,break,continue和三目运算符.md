<center><h2>方法、break、continue和三目运算符</h2></center>

##### 1. 方法【练】

###### 1.1 为什么使用方法

```java
Scanner sc = new Scanner(System.in);

sc.nextInt();
sc.nextLine().charAt(0);

一段代码你是用了三遍，请把它封装成一个方法
一堆方法你使用了三遍，请把它封装成一个工具类
一个工具类你使用了三遍，请把它写成一个博客
开发中会重复使用到很多的功能性代码，循环的利用并不能完全解决问题
    1. 代码过于臃肿
    2. 代码阅读性极差
   	3. 代码维护性极差
```

###### 1.2 比葫芦画瓢

```java
public static void main(String[] args) {
    
}
public static: 后续学习
void: 返回值类型，这里使用void表示当前的方法没有返回值！！！
main: 方法名，要求见名知意，动宾结构，小驼峰命名法
(String[] args): 形式参数列表，形参
{}: 方法体，需要封装的功能代码
    
形式参数列表：
    如厨师做饭，需要的材料清单
返回值类型：
    是当前方法运行结束之后给予调用方法位置的反馈
    
总结方法定义的格式：
    public static 返回值类型 方法名(形式参数列表) {
    
}

方法定义的位置：
    1. class大括号以内
    2. 其他方法的大括号之后
    
```

###### 1.3 无参数无返回值的方法

```java
/* 
需求：
	展示一个HelloWorld
方法分析：
	public static
	方法名：printHelloWorld
	形式参数列表：不需要参数
	返回值类型：不需要返回值 void
	
	一般注释：
	单行注释 // 
	多行注释 /* */
	文档注释:
		/**
		* printHelloWorld方法是通过System.out展示一个Hello World
		*/

*/
public static void printHelloWrld() {
    System.out.println("Hello World");
}

// 调用方法一定有小括号,同一个方法可以重复调用
printHelloWrld();
```

###### 1.4 有参数无返回值的方法

```java
/*
需求：
	展示用户提供的int类型数据
方法分析：
	public static
	方法名：printInt
	形式参数列表：int 这里需要用户传入int类型的数据，所以给予int类型的形式参数
	返回值类型：不需要返回值 void
*/

/**
* 该方法是展示用户提供的int类型数据
* @param num
*		int类型数据，需要用户调用时提供
*/
public static void printInt(int num) {
    System.out.println(num);
}

// 方法调用
printInt(200); // 200赋值给了num，打印num的时候就会输出200
```

###### 1.5 无参数有返回值的方法

```java
/*
需求：
	give me Five 给我一个5
方法分析：
	public static
	方法名：giveFive
	形式参数列表：不需要参数
	返回值类型：int
*/

/**
* 给方法的调用者，返回一个5
* @return 
*	返回值类型是一个int类型
*/
public static int giveFive() {
    /*
    return 关键字：
    	1. 方法运行到return关键字，之后的代码不会继续运行，终止当前方法
    	2. return可以把 关键字之后的数据，返回到方法之外
    */
    return 5;
}

// 方法调用
int num = giveFive();
```

###### 1.6 有参数有返回值的方法

```java
/*
需求：
	获取两个数之和！
方法分析：
	public static
	方法名：getSumOfTwoNumber
	形式参数列表：int num1, int num2
	返回值类型：int
*/

/**
* 获取两个int类型数据之和
* @param num1
*	int类型数据
* @param num2
*	int类型数据
* @return
*	返回值是两个int类型数据之和，也是int类型
*/
public static int getSumOfTwoNumber(int num1, int num2) {
    return num1 + num2;
} 

// 方法调用
int sum = getSumOfTwoNumber(1,2);
```

##### 2. break关键字

```java
字面含义：
	打破
代码中的含义：
	1. 跳出switch-case 结构
	2. 跳出循环！！！
演示代码：
class TestBreak {
    public static void main(String[] args) {
        /*
        for (int i = 0; i < 10; i++) {
            if (6 == i) {
                System.out,println("循环终止");
                break;
            }
          
            System.out.ptintln(i);
            
            order();
        }
        */
        
        public static void order () {
            
            int choose = 0;
            boolean flag = false;
            Scanner sc = new Scanner(System.in);
            
            while (true) {
                System.out.ptintln("客官，你点点儿啥？");
                System.out.ptintln("1. 烤面筋");
                System.out.ptintln("2. 鸡蛋灌饼");
                System.out.ptintln("3. 炸串串");
                System.out.ptintln("4. 肉夹馍");
                System.out.ptintln("5. 下单");
            
            	choose = sc.nextInt();
            
                switch (sc) {
                    case 1：
                        System.out.ptintln("1.5一串");
                        break;
                    case 2：
                        System.out.ptintln("4块");
                        break;
                    case 3：
                        System.out.ptintln("12块钱");
                        break;
                    case 4：
                        System.out.ptintln("5块钱");
                        break;
                    case 5：
                        flag = true;
                        break;
                }
            }
            
            if (flag){
                System.out.ptintln("下单");
                break; //跳出while循环结构
            }
        }
    }
}
```

##### 3. continue关键字

```
字面含义：
	继续
代码中的功能：
	结束本次循环，直接进入下一次循环！！！
	
使用建议：
	1. continue关键字不建议和while循环以及do-while循环连用
	2. continue关键字用于for循环的时候。可以有效地影响for循环的变更
```

##### 4.三目运算符

```
三目运算符属于条件运算符
condition ? true 处理方式是 ? false 处理方式
例如:
	return num1 > num2 ? num1 : num2
	当num1 > num2 条件为true时，返回为num1
	当num1 < num2 条件为false时，返回为num2
```







