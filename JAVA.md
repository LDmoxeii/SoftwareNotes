# JAVA

## 基础

### `this` & `super`

>`this`
 > - 一是引用隐性参数^[你猜]
> - 二是调用该类其他的构造器

> `super` 
> - 一是调用超类^[已存在的类]的方法
> - 二是调用超类^[已存在的类]的构造器。


>在调用构造器的时候，这两个关键字的使用方式很相似。调用构造器的语句只能作为另一个构造器的第一条语句出现。构造参数既可以传递给本类 `(this)` 的其他构造器，也可以传递给超类 `(super)` 的构造器。



### System

>如果查看一下 `System` 类，就会发现有一个 `setOut`方法，它可以将 `System.out` 设置为不同的流。读者可能会感到奇怪，为什么这个方法可以修改final变量的值。原因在于， `setOut` 方法是一个本地方法，而不是用 `Java` 语言实现的。本地方法可以绕过 `Java` 语言的存取控制机制。这是一种特殊的方法，在自己编写程序时，不应该这样处理。

>  `System.exit`  可指定运行返回值

### Unicode

>  `Unicode`  转义序列会在解析代码之前得到处理。

### 变量声明

> 在  `Java`  中，变量的声明尽可能地靠近变量第一次使用的地方，这是一种良好的程序编写风格



### static

> 注释：可以使用对象调用静态方法。我们建议使用类名，而不是对象来调用静态方法。

>在下面两种情况下使用静态方法：
>- 一个方法不需要访问对象状态，其所需参数都是通过显式参数提供（例如：Math.pow)。
>- 一个方法只需要访问类的静态域（例如：Employee..getNextId)。

### final

> 关键字final表示这个变量只能被赋值一次。一旦被赋值之后，就不能够再更改了。习惯上，常量名使用全大写  

### switch

>如果你比我们更喜欢 `switch` 语句，编译代码时可以考虑加上 `###Xlint:fallthrough` 选项，
>如下所示：
> `javac ###Xlint:fallthrough Test.java`
>这样一来，如果某个分支最后缺少一个 `brak` 语句，编译器就会给出一个警告消息。
>如果你确实正是想使用这种“直通式 `”(fallthrough)` 行为，可以为其外围方法加一个
>标注 `@Suppress Warnings("fallthrough")` 这样就不会对这个方法生成警告了。

### continue
> `continue` 语句将控制转移到最内层循环的首部



### 带标签的break语句
>有时候，在嵌套很深的循环语句中会发生一些不可预料的事情。此时可能更加希望跳到嵌套的所有循环语句之外。通过添加一些额外的条件判断实现各层循环的检测很不方便。
这里有一个示例说明了 `break` 语句的工作状态。
>请注意，标签必须放在希望跳出的最外层循环之前，并且必须紧跟一个冒号。

```java
Scanner in new Scanner(System.in);
int n;
read data:
while (...)//this loop statement is tagged with the label
{
	...
    for (...)//this inner loop is not labeled
    {
		System.out.print("Enter a number >0:");
		n in.nextInt();
		if (n<0)//should never happen###can't go on
		break read_data;
		//break out of read_data loop
		...
	}
}
//this statement is executed immediately after the labeled break
if (n 0)//check for bad situation
{
//deal with bad situation
}
else
{
//carry out normal processing
```

### 方法调用
> `Java` 程序设计语言总是采用按值调用。
> - 方法得到的是所有参数值的一个拷贝。
> - 
> - 
> - 方法不能修改传递给它的任何参数变量的内容。

> 方法参数共有两种类型：
> - 基本数据类型（数字、布尔值）
> - 对象引用。

>通过不同对象访问同一类可达成数据的修改

>方法参数的使用情况：
> - 一个方法不能修改一个基本数据类型的参数（即数值型或布尔型）。
> - 一个方法可以改变一个对象参数的状态。
> - 一个方法不能让对象参数引用一个新的对象。

  

### 初始化数据域
> 三种初始化方法：
> - 构造域中设置值
> - 声明中赋值
> - 初始化块^[只要构造类的对象，块就会被执行]

### 导入^[一个类可以使用所属包中的所有类，以及其他包中的公有类(public class)]
> - 第一种方式是在每个类名之前添加完整的包名
> - import语句导入一个特定的类或者整个包
> 	- 类
> 	-  静态方法
> 	-  静态域
## 特殊浮点数值

```java
Double.POSITIVE INFINITY //无穷大 
Double.NEGATIVE INFINITY //无穷小
Double.NaN				 //非数	
Double.BigInteger		 //大整型
Double.BigDecimal		 //大浮点
//大数值类需要使用add和multiply等方法 
 
```

```java
if (x =Double.NaN)//is never true
//所有“非数值”的值都认为是不相同的。然而，可以使用Double.isNaN方法：
if (Double.isNaN(x))//check whether x is "not a number"
```

>强制类型转换通过截断小数部分将浮点值转换为整型。

>短路求值 --> 如果第一个操作数已经能够确定表达式的值，第二个操作数就不必计算了。

## JAVAAPI

###  `Math`

```java
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

###  `BigInteger`

```java
BigInteger add(BigInteger other)
BigInteger subtract(BigInteger other)
BigInteger multiply(BigInteger other)
BigInteger divide(BigInteger other)
BigInteger mod(BigInteger other)
//返回这个大整数和另一个大整数other的和、差、积、商以及余数。
int compareTo(BigInteger other)
//如果这个大整数与另一个大整数other相等，返回0；如果这个大整数小于另一个大整数other,.返回负数；否则，返回正数。
static BigInteger valueof(long x)//返回回值等于x的大整数。
BigInteger multiply(BigInteger other)
BigInteger divide(BigInteger other)
BigInteger mod(BigInteger other)
//返回这个大整数和另一个大整数other的和、差、积、商以及余数。
int compareTo(BigInteger other)
//如果这个大整数与另一个大整数other相等，返回0；如果这个大整数小于另一个大整数other,返回负数；否则，返回正数。
static BigInteger valueof(long x)//回值等于x的大整数。
BigDecimal add(BigDecimal other)
BigDecimal subtract(BigDecimal other)
BigDecimal multiply(BigDecimal other)
BigDecimal divide(BigDecimal other RoundingMode mode)
//返回这个大实数与另一个大实数other的和、差、积、商。须给出舍入方式( rounding mode ) 。 RoundingMode.HALF_UP 等。有关其他的舍入方式请参看API文档。
int compareTo(BigDecimal other)
//如果这个大实数与另一个大实数相等，返回0；如果这个大实数小于另一个大实数，返回负数否则，返回正数。
static BigDecimal valueof(long x)
static BigDecimal valueof(long x,int scale)//返回值为x或x/10 scale的一个大实数。
```

###  `Strting`

```java
char charAt (int index)//返回位置 n 的代码单元， n 介于0~s.length0###1之间
int codePointAt(int index)//返回从给定位置开始的码点。
int offsetByCodePoints(int startIndex,int cpCount)
//返回从startIndex代码点开始，位移cpCount后的码点索引。
int compareTo(String other)
//按照字典顺序，如果字符串位于other之前，返回一个负数；如果字符串位于other之后，返回一个正数；如果两个字符串相等，返回0。
Intstream codePoints()
//将这个字符串的码点作为一个流返回。调用toArray将它们放在一个数组中。
new String(int[]codePoints,int offset,int count)
//用数组中从offset开始的count个码点构造一个字符串。
boolean equals(object other)
//如果字符串与other相等，返回truee
boolean equalsIgnoreCase(String other)
//如果字符串与other相等（忽略大小写），返回true。
boolean startswith(string prefix)
boolean endswith(string suffix)
//如果字符串以suffix开头或结尾，则返回trues
int indexof(String str)
int indexof(String str,int fromIndex)
int indexof(int cp)
int indexof(int cp,int fromIndex)
//返回与字符串s或代码点cp匹配的第一个子串的开始位置。这个位置从索引0或fromIndex开始计算。如果在原始串中不存在str,返回###1。
int lastIndexof(String str)
int lastIndexof(String str,int fromIndex)
int lastindexof(int cp)
int lastindexof(int cp,int fromIndex)
//返回与字符串str或代码点cp匹配的最后一个子串的开始位置。这个位置从原始串尾端或fromIndex开始计算。
int length()
//返回字符串的长度。返回采用UTF###l6编码表示的给定字符串所需要的代码单元数量。
int codePointCount(int startIndex,int endIndex)
//返回startIndex和endIndex######1之间的码点数量.没有配成对的代用字符将计入代码点。
String replace(CharSequence oldstring,CharSequence newstring)
//返回一个新字符串。这个字符串用newString代替原始字符串中所有的oldString。可以用String或StringBuilder对象作为CharSequence参数。
String substring(int beginIndex)
String substring(int beginIndex,int endIndex)
//返回一个新字符串。这个字符串包含原始字符串中从beginIndex到串尾或endIndex######l的所有代码单元。
String toLowercase()
String toUppercase()
//返回一个新字符串。这个字符串将原始字符串中的大写字母改为小写，或者将原始字符串中的所有小写字母改成了大写字母。
String trim()
//返回一个新字符串。这个字符串将删除了原始字符串头部和尾部的空格。
String join(CharSequence delimiter,CharSequence...elements)
//返回一个新字符串，用给定的定界符连接所有元素。
```

>在API注释中，有一些 `CharSequence` 类型的参数。这是一种接口类型，所有字符
串都属于这个接口。一个 `CharSequence` 形参，完全可以传入 `String` 类型的实参。
###  `StringBulider`

```java
StringBuilder()
//构造一个空的字符串构建器。
int length()
//返回构建器或缓冲器中的代码单元数量。
StringBuilder append(string str)
//追加一个字符串并返回this。
StringBuilder append(char c)
//追加一个代码单元并返回this。
StringBuilder appendCodePoint(int cp)
//追加一个代码点，并将其转换为一个或两个代码单元并返回this。
void setcharAt(int i,char c)
//将第i个代码单元设置为c。
StringBuilder insert(int offset,string str)
//在offset位置插入一个字符串并返回his。
StringBuilder insert(int offset,char c)
//在offset位置插入一个代码单元并返回this。
StringBuilder delete(int startIndex,int endIndex)
//删除偏移量从startIndex到###endIndex###1的代码单元并返回this。
String tostring()
//返回一个与构建器或缓冲器内容相同的字符串。
```

###  `Scanner`

```java
Scanner (Inputstream in)
//用给定的输入流创建一个Scanner对象。
String nextLine(
//读取输入的下一行内容。
String next()
//读取输入的下一个单词（以空格作为分隔符）。
int nextInt(
double nextDouble(
//读取并转换下一个表示整数或浮点数的字符序列。
boolean hasNext()
//检测输入中是否还有其他单词。
boolean hasNextInt()
boolean hasNextDouble()
//检测是否还有表示整数或浮点数的下一个字符序列。
static Console console()
//如果有可能进行交互操作，就通过控制台窗口为交互的用户返回一个Console对象，否则返回null。对于任何一个通过控制台窗口启动的程序，都可使用Console对象。否则，其可用性将与所使用的系统有关。
static char[]readPassword(String prompt,Object...args)
static String readLine(String prompt,Object...args)
//显示字符串prompt并且读取用户输人，直到输入行结束。args参数可以用来提供输入格式。有关这部分内容将在下一节中介绍。
```

###  `ScannerByFile`

```java
Scanner(File f)
//构造一个从给定文件读取数据的Scanner。
Scanner(String data)
//构造一个从给定字符串读取数据的Scanner。
PrintWriter(string fileName)
//构造一个将数据写入文件的Print Writer。文件名由参数指定。
static Path get(string pathname)
//根据给定的路径名构造一个Path。
```

### `LocalDate`
```java
static LocalTime now()
//构造一个表示当前日期的对象。
static LocalTime of(int year,int month,int day)
//构造一个表示给定日期的对象。
int getYear()
int getMonthValue()
int getDayofMonth()
//得到当前日期的年、月和日。
DayofWeek getDayofWeek
//得到当前日期是星期几，作为DayOfWeek类的一个实例返回。调用getValue来得到1~7之间的一个数，表示这是星期几，1表示星期一，7表示星期日。
LocalDate plusDays(int n)
LocalDate minusDays(int n)
//生成当前日期之后或之前n天的日期。
```

## 位运算

### `<<` ==> 左移运算符

> 左移一位

### `>>` ==> 右移运算符

> 右移一位 

>左移一位后的数值经过计算可以发现刚好值位移前数值的两倍，等价于乘2操作，在很多情况下可以当做乘2使用，但是并不代表真正的乘2，在一些特殊情况下并不等价

>所以根据这个规则，如果任意一个十进制的数左位移32位，右边补位32个0，十进制岂不是都是0了？当然不是！！！ 当int 类型的数据进行左移的时候，当左移的位数大于等于32位的时候，位数会先求余数，然后用该余数进行左移，也就是说，如果真的左移32位的时候，会先进行位数求余数，即为左移32位相当于左移0位 ，所以左移33 的值和左移一位1 是一样的

>位运算以补码形式进行运算 

## 字符串
### 码点与代码单元
>Java字符串由char值序列组成。char数据类型是一个采用UTF-16编码表Unicode码点的代码单元。大多数的常用Unicode字符使用一个代码单元就可以表示，而辅助字符需要一对代码单元表示。

### 输入密码
>注释：因为输入是可见的，所以 `Scanner` 类不适用于从控制台读取密码。 `Console` 类实现。要想读取一个密码，可以采用下列代码：
```java
	`Console cons System.console();`
	`String username cons.readLine("User name:");`
	`char[] passwd cons.readPassword("Password:");`
 ```
>为了安全起见，返回的密码存放在一维字符数组中，而不是字符串中。在对密码进行处理之后，应该马上用一个填充值覆盖数组元素。
i
>采用 `Console` 对象处理输入不如采用 `Scanner` 方便。每次只能读取一行输入，而没有能够读取一个单词或一个数值的方法。

### 文件输入
>要想对文件进行读取，就需要一个用File对象构造一个 `Scanner` 对象，如下所示：
> `Scanner in new Scanner(Paths.get("myfile.txt"),"UTF-8");`

### 构建字符串
```java
//如果需要用许多小段的字符串构建一个字符串，那么应该按照下列步骤进行。首先，构建一个空的字符串构建器：
StringBuilder builder new StringBuilder();
//当每次需要添加一部分内容时，就调用append方法。
builder.append(ch);//appends a single character
builder.append(str);//appends a string
//在需要构建字符串时就调用toString方法，将可以得到一个String对象，其中包含了构建器中的字符序列。
String completedString builder.toString();
```

## 工厂方法
### 静态工厂方法
### 更改器工厂方法

对象状态会改变
>LocalDate类没有更改器方法，与之不同，Date类有一个更改器方法setTime,可以
在这里设置毫秒数。Dte对象是可变的，这一点就破坏了封装性！

>请看下面这段代码：
```java
Employee harry =...//实例化对象
Date d=harry.getHireDay();//return hireDay
double tenYearsInMilliSeconds =10 365.25 24 60 60 1000;
d.setTime(d.getTime()###(long)tenYearsInMilliSeconds);
//let's give Harry ten years of added seniority
```

>出错的原因很微妙。d和hary.hireDay引用同一个对象。对d调用
更改器方法就可以自动地改变这个雇员对象的私有状态！

>如果需要返回一个可变对象的引用，应该首先对它进行克隆（clone)。对象clone是
指存放在另一个位置上的对象副本。

![[Pasted image 20230228144147.png]]

>下面是修改后的代码：

```java
class Employee{
	...
	public Date getHi reDay(){
		return (Date)hireDay.clone();//0k
	}
	...
}
```

>凭经验可知，如果需要返回一个可变数据域的拷贝，就应该使用clone。

### 访问器工厂方法

>只访问对象不改变状态

### 静态工厂方法
## 构造器
### 构造器处理步骤
> - 所有数据域被初始化为默认值（0、false或null)。
> - 按照在类声明中出现的次序，依次执行所有域初始化语句和初始化块。
> - 如果构造器第一行调用了第二个构造器，则执行第二个构造器主体。
> - 执行这个构造器的主体
### 调用另一个构造器
 >关键字 `this` 引用方法的隐式参数。然而，这个关键字还有另外一个含义。如果构造器的第一个语句形如 `this(...)` ,这个构造器将调用同一个类的另一个构造器。
 > - 下面是一个典型的例子：
```java
public Employee(double s){
//calls Employee(String,double)
	this("Employee #" + nextId,s);
	nextId++;
}
```
> - 当调用 `new Employee(60000)` 时， `Employee(double)` 构造器将调用 `Employee(String,double)` 构造器。
> - 采用这种方式使用 `this` 关键字非常有用，这样对公共的构造器代码部分只编写一次即可。

## 类设计技巧
-  一定要保证数据私有
> 这是最重要的；绝对不要破坏封装性。有时候，需要编写一个访问器方法或更改器方法，但是最好还是保持实例域的私有性。很多惨痛的经验告诉我们，数据的表示形式很可能会改变，但它们的使用方式却不会经常发生变化。当数据保持私有时，它们的表示形式的变化不会对类的使用者产生影响，即使出现bug也易于检测。
- 一定要对数据初始化
>Java不对局部变量进行初始化，但是会对对象的实例域进行初始化。最好不要依赖于系统的默认值，而是应该显式地初始化所有的数据，具体的初始化方式可以是提供默认值，也可以是在所有构造器中设置默认值。

- 不要在类中使用过多的基本类型
>就是说，用其他的类代替多个相关的基本类型的使用。这样会使类更加易于理解且易于修改。
> - 例如，用一个称为Address的新的类替换一个Customer类中以下的实例域：
```Java
private String street;
private String city;
private String state;
private int zip;
```
>这样，可以很容易处理地址的变化，例如，需要增加对国际地址的处理。

- 不是所有的域都需要独立的域访问器和域更改器
>或许，需要获得或设置雇员的薪金。而一旦构造了雇员对象，就应该禁止更改雇用日期，并且在对象中，常常包含一些不希望别人获得或设置的实例域，例如，在Address类中，存放州缩写的数组。

- 将职责过多的类进行分解
>这样说似乎有点含糊不清，究竟多少算是“过多”？每个人的看法不同。但是，如果明显地可以将一个复杂的类分解成两个更为简单的类，就应该将其分解。
- 类名和方法名要能够体现它们的职责
>与变量应该有一个能够反映其含义的名字一样，命名类名的良好习惯是采用一个名词(Order)、前面有形容词修饰的名词(RushOrder)或动名（有“-ing”后缀）修饰名词（例如，BillingAddress)。

- 优先使用不可变的类
