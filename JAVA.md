# JAVA

## 基础

>  `System.exit`  可指定运行返回值

>  `Unicode`  转义序列会在解析代码之前得到处理。

> 在  `Java`  中，变量的声明尽可能地靠近变量第一次使用的地方，这是一种良好的程序编写风格

> 关键字final表示这个变量只能被赋值一次。一旦被赋值之后，就不能够再更改了。习惯上，常量名使用全大写 

## 特殊浮点数值

```java
Double.POSITIVE INFINITY 
Double.NEGATIVE INFINITY
Double.NaN
```

```java
if (x =Double.NaN)//is never true
//所有“非数值”的值都认为是不相同的。然而，可以使用Double.isNaN方法：
if (Double.isNaN(x))//check whether x is "not a number"
```

![数据转换](C:\Users\LD_moxeii\AppData\Roaming\Typora\typora-user-images\image-20230226175012134.png)

>强制类型转换通过截断小数部分将浮点值转换为整型。
>短路求值 -- > 如果第一个操作数已经能够确定表达式的值，第二个操作数就不必计算了。

## JAVAAPI

```java
//Math
Math.sqrt()//square : 平方	//取余运算在计算商值向0方向舍弃小数位
Math.pow()//pow : 幂			//取模运算在计算商值向负无穷方向舍弃小数位
Math.floorMod()//floor : 模
Math.sin()//三角函数
Math.cos()
Math.tan()
Math.atan()
Math.atan2()
Math.exp()//指数函数
Math.log()//自然对数
Math.log10()//以十为底对数
Math.PI //π
Math.E//自然数
```

## 位运算
### `<<` ==> 左移运算符
> 左移一位


### `>>` ==> 右移运算符
> 右移一位 

>左移一位后的数值经过计算可以发现刚好值位移前数值的两倍，等价于乘2操作，在很多情况下可以当做乘2使用，但是并不代表真正的乘2，在一些特殊情况下并不等价

>所以根据这个规则，如果任意一个十进制的数左位移32位，右边补位32个0，十进制岂不是都是0了？当然不是！！！ 当int 类型的数据进行左移的时候，当左移的位数大于等于32位的时候，位数会先求余数，然后用该余数进行左移，也就是说，如果真的左移32位的时候，会先进行位数求余数，即为左移32位相当于左移0位 ，所以左移33 的值和左移一位1 是一样的

>位运算以补码形式进行运算 


