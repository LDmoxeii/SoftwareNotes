# 查找

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
```

# 筛选

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

## 素数

```java
           int temp;
        for (int nums = 2; nums <= 100; nums++) {// nums=素数
            temp = 0;
            for (int except = 2; except <= Math.sqrt(nums); except++) {
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

# 排序

## 冒泡

```java
        int[] arr = new int[5];
        // 标记是否一轮未进行交换，即排序完成
        // 第一次需要进入循环验证，必须为true
        boolean flag = true;
        while (flag) {
            // 每次开始循环,即设置还未交换
            flag = false;
            // border:尾边界
            for (int index = 0, border = arr.length; index < border - 1; index++, border--) {
                if (arr[index] > arr[index + 1]) {
                    arr[index] = arr[index + 1] ^ arr[index];
                    arr[index + 1] = arr[index + 1] ^ arr[index];
                    arr[index] = arr[index + 1] ^ arr[index];
                    // 已进行交换，故为true
                    flag = true;
                }
            }
        }
    }
```

# 数学

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
         */
        while (temp1 != temp2) {
            if (temp1 > temp2) {
                temp1 -= temp2;
            } else {
                temp2 -= temp1;
            }

        }
        /**
         * 几何原本：辗转相除法 1.a÷b，令r为所得余数（0≤r＜b）。若r=0，算法结束；b即为答案； 2.互换：置a←b，b←r，并返回第一步。
         */
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

# 位运算

## 2的幂

```java
int num;
if(num & num-1)
	reture ture;
else
	reture 0;
```

## 4的幂

```java
int num;
if(num & num-1 && num % 3 == 0)
	reture ture;
else
	trture 0;
```

## 位1的个数

```java
int num,c;
if(num!=0)
	num &= (num-1);
	++c;
```

## 交换数字

```java
int a[];
a[0]=a[0]^a[1];
a[1]=a[0]^a[1];
a[0]=a[0]^a[1];
```

# 杂项

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