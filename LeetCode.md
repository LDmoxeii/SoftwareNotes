# C

## 二分查找

```java
int left = 0;
        int right = len - 1;
        while (left < right) {
            int mid = (left + right) / 2;
            if (nums[mid] < target) {
                left = mid + 1;
            } else if (nums[mid] >= target) {
                right = mid;
            }
```

## 数组合并

```java
//合并
int[][] res = new int[intervals.length][2];
        int idx = -1;
        for (int[] interval: intervals) {
            // 如果结果数组是空的，或者当前区间的起始位置 > 结果数组中最后区间的终止位置，说明不重叠。
            // 则不合并，直接将当前区间加入结果数组。
            if (idx == -1 || interval[0] > res[idx][1]) {
                res[++idx] = interval;
            } else {
                // 反之说明重叠，则将当前区间合并至结果数组的最后区间
                res[idx][1] = Math.max(res[idx][1], interval[1]);
            }
        }
        return Arrays.copyOf(res, idx + 1);
```

## stream流使用

```java
//1.
Arrays.sort(intervals, (v1, v2) -> v1[0] - v2[0]);
//2.
int total = Arrays.stream(nums).sum();
```

## 完数

```c
#include<stdio.h>
int main()
{
    int i, j, s, n;  /*变量i控制选定数范围，j控制除数范围，s记录累加因子之和*/
    printf("请输入所选范围上限：");
    scanf("%d", &n);  /* n的值由键盘输入*/
    for( i=2; i<=n; i++ )
    {
        s=0;  /*保证每次循环时s的初值为0*/
        for( j=1; j<i; j++ )
        {
            //关键
            if(i%j == 0)  /*判断j是否为i的因子*/
                s += j;
        }
        if(s == i)  /*判断因子这和是否和原数相等*/
            printf("It's a perfect number:%d\n", i);
    }
    return 0;
}
```

## 水仙花数

```c
#include <stdio.h>
int main()
{
    int hun, ten, ind, n;
    printf("result is:");
    for( n=100; n<1000; n++ )  /*整数的取值范围*/
    {
        hun = n / 100;								//百位数
        ten = (n-hun*100) / 10;						//十位数	
        ind = n % 10;								//个位数
        if(n == hun*hun*hun + ten*ten*ten + ind*ind*ind)  /*各位上的立方和是否与原数n相等*/
            printf("%d  ", n);
    }
    printf("\n");
   
    return 0;
}
```

素数

```CQL
//思路1
#include <stdio.h>

int main(){
    int a=0;  // 素数的个数
    int num=0;  // 输入的整数

    printf("输入一个整数：");
    scanf("%d",&num);

    for(int i=2;i<num;i++){
        if(num%i==0){
            a++;  // 素数个数加1
        }
    }

    if(a==0){
        printf("%d是素数。\n", num);
    }else{
        printf("%d不是素数。\n", num);
    }

    return 0;
}
//思路2
#include <stdio.h>
#include <math.h>
void main(){
    int m;  // 输入的整数 
    int i;  // 循环次数
    int k;  // m 的平方根 

    printf("输入一个整数：");
    scanf("%d",&m);

    // 求平方根，注意sqrt()的参数为 double 类型，这里要强制转换m的类型 
    k=(int)sqrt( (double)m );
    for(i=2;i<=k;i++)
        if(m%i==0)
            break;

    // 如果完成所有循环，那么m为素数
    // 注意最后一次循环，会执行i++，此时 i=k+1，所以有i>k 
    if(i>k)
        printf("%d是素数。\n",m);
    else
        printf("%d不是素数。\n",m);

    return 0;
}
```

## 冒泡

```c
#include <stdio.h>
//交换 a 和 b 的位置的函数
#define N 5
int a[N] = { 5,1,4,2,8 };
void swap(int *a, int *b);
//这是带输出的冒泡排序实现函数，从输出结果可以分析冒泡的具体实现流程
void BubSort_test();
//这是不带输出的冒泡排序实现函数，通过此函数，可直接对数组 a 中元素进行排序
void BubSort_pro();
int main()
{
    BubSort_test();
    return 0;
}
void swap(int *a, int *b) {
    int temp;
    temp = *a;
    *a = *b;
    *b = temp;
}

//这是带输出的冒泡排序实现函数，从输出结果，可以看到冒泡的具体实现流程
void BubSort_test() {
    for (int i = 0; i < N; i++) {
        //对待排序序列进行冒泡排序
        for (int j = 0; j + 1 < N - i; j++) {
            //相邻元素进行比较，当顺序不正确时，交换位置
            if (a[j] > a[j + 1]) {
                swap(&a[j], &a[j + 1]);
            }
        }
        //输出本轮冒泡排序之后的序列
        printf("第%d轮冒泡排序：", i + 1);
        for (int i = 0; i < N; i++) {
            printf("%d ", a[i]);
        }
        printf("\n");
    }
}

//这是不带输出的冒泡排序实现函数，通过此函数，可直接对数组 a 中元素进行排序
void BubSort_pro() {
    for (int i = 0; i < N; i++) {
        //对待排序序列进行冒泡排序
        for (int j = 0; j + 1 < N - i; j++) {
            //相邻元素进行比较，当顺序不正确时，交换位置
            if (a[j] > a[j + 1]) {
                swap(&a[j], &a[j + 1]);
            }
        }
    }
}
```

# JAVA

## 冒泡

```java
   public void BubbleSort() {
        // Scanner scanner = new Scanner(System.in);
        // for(int i = 0; i < arr.length; i++){
        // arr[i]= scanner.nextInt();
        // }
        int[] arr = new int[5];
        for (int i = 0; i < arr.length; i++) {
            Random random = new Random();
            arr[i] = random.nextInt();
        }
        // 标记是否一轮未进行交换，即排序完成
        // 第一次需要进入循环验证，必须为true
        boolean flag = true;
        while (flag) {
            // 每次开始循环,即设置还未交换
            flag = false;
            // border:尾边界
            for (int j = 0, border = arr.length; j < border - 1; j++, border--) {
                if (arr[j] > arr[j + 1]) {
                    // int temp;
                    // temp=arr[j];
                    // arr[j]=arr[j+1];
                    // arr[j+1] = temp
                    // 使用异或可不使用temp
                    arr[j] = arr[j + 1] ^ arr[j];
                    arr[j + 1] = arr[j + 1] ^ arr[j];
                    arr[j] = arr[j + 1] ^ arr[j];
                    // 已进行交换，故为true
                    flag = true;
                }
            }
        }
        for (int i = 0; i < arr.length; i++) {
            System.out.println("arr[i] = " + arr[i]);
        }
    }
```

## 素数

```jav
   
   public void PrimeNumber() {
        int temp;
        for (int nums = 2; nums <= 100; nums++) {// nums=素数
            temp = 0;
            for (int except = 2; except <= (nums / 2); except++) {
                if (nums % except == 0) {
                    temp = 1;
                    break;
                }
            }

            if (temp == 0) {
                System.out.println(nums + "是素数");
            }

        }
    }
```

## 最大公因数:最小公倍数

```java
  public void commonNumber() {
        Random random = new Random();
        int num1 = random.nextInt(101);
        int num2 = random.nextInt(101);
        int temp1 = num1 = 36;
        int temp2 = num2 = 96;
        /**
         * 九章算数：更相减损术 以少减多,更相减损,求其等也,以等数约之 等数约之,即除也,其所以相减者皆等数之重叠, 故以等数约之
         **/
        while (temp1 != temp2) {
            if (temp1 > temp2) {
                temp1 -= temp2;
            } else {
                temp2 -= temp1;
            }

        }
        /**
         * 几何原本：辗转相除法 1.a÷b，令r为所得余数（0≤r＜b）。若r=0，算法结束；b即为答案； 2.互换：置a←b，b←r，并返回第一步。
         **/
        int remainder;

        while (temp1 != 0)

        {

            remainder = temp1 % temp2;

            temp1 = temp2;

            temp2 = remainder;

        }

        System.out.println("最大公约数 = " + temp2);
        System.out.println("最小公倍数 = " + (num1 * num2) / temp1);
    }
```

## 阶乘

```java
    public void Factorial() {
        Random random = new Random();
        int border = random.nextInt(11);
        int sum=0;
        int cardinality=1;
        for (int i = 1; i <= 10; i++) {
            cardinality*=i;
            sum+=cardinality;
        }
        System.out.println(sum);
    }
```

