# 基本公式

$\Large u^v=e^{v\ln{}{u}} $

# 三角函数

$\Large\arccos x$ 定义域为：$\Large\left [ -1,1 \right ] $ 值域为:${\Large \left [ 0,\pi  \right ]}$ 

$\Large\arcsin x $ 定义域为：$\Large\left [ -1,1 \right ]  $ 值域为：${\Large \left [ -\frac{\pi}{2} ,\frac{\pi}{2}  \right ] } $

$\Large\arctan x$ 定义域为：$\R$ 值域为：${\Large \left ( -\frac{\pi}{2} ,\frac{\pi}{2}  \right ) } $

$$
\Large推导\\
\Large\sec^2x-\tan^2x=1​\\

\Large\because\tan^2x+1=1+\frac{sin^2 x}{cos^2 x} ​\\
 =\Large\frac{\cos^2 x+\sin x}{\cos^2 x}​\\

=\Large\frac{1}{\cos^2 x}​\\
=\Large\sec^2 x\\
$$
$$
\Large积化和差公式\\
\Large\sin\alpha\cos\beta=\frac{1}{2}[\sin（\alpha+\beta）+\sin(\alpha-\beta)]\\
\Large\cos\alpha\cos\beta=\frac{1}{2}[\cos(\alpha+\beta)+\cos(\alpha-\beta)]\\
\Large\sin\alpha\sin\beta=-\frac{1}{2}[\cos(\alpha+\beta)-\cos(\alpha-\beta)]\\
\Large和差化积公式\\
\Large\sin\alpha+\sin\beta=2\sin\frac{\alpha+\beta}{2}\cos\frac{\alpha-\beta}{2}\\
\Large\cos\alpha+\cos\beta=2\cos\frac{\alpha+\beta}{2}\cos\frac{\alpha-\beta}{2}\\
\Large\cos\alpha-\cos\beta=-2\sin\frac{\alpha+\beta}{2}\sin\frac{\alpha-\beta}{2}\\
$$

$$
\Large 三角函数转换\\
\Large \sec x=\frac{1}{\cos x}\\
\Large \csc x=\frac{1}{\sin x}\\
\Large \cot x=\frac{1}{\tan x}\\
$$


## 等价无穷小

$$
\Large　分子或分母为某项乘积时可用\\
\Large \sin x \sim x\\
\Large 1-\cos x\sim \frac{1}{2}x^2 \\
\Large \tan x \sim x\\
\Large \arctan x \sim x\\
\Large \arcsin x \sim x\\
\Large a^x-1\sim x\ln{}{a}\\
\Large \ln{}{(1+x)}\sim x\\
\Large 1+x\sim e^x\\
\Large\sqrt[n]{1+x}-1 \sim \frac{1}{n}x\\
$$



# 极限

## 重要极限

$$
\Large\lim_{x\to\infty}(1+\frac{1}{x})=e\\
$$

$$
\Large\lim_{x\to0}(\frac{x+a}{x+b})^{cx}
$$

$\Large x$ 可换元

# 间断点


## 第一类间断 *其中一边无极限定义*

### 一可跳

1. 可去间断
2. 跳跃间断

## 第二类间断 *有左右极限*

### 二无荡
1. 无穷间断
2. 振荡间断


# 导数

## 反函数求导法则

定理：$\Large x=f(y)$在$\Large I_g$内单调且可导$\Large f(y)\ne0$

反函数$\Large y=f^{-1}(x)$

$\Large [f^{-1}(x)]'=\frac{1}{f'(y)}$

## 求导表
$$
\Large(\tan x)'=\sec^2=\frac{1}{\cos^2 x}\\
\Large(\cot x)'=-\csc^2 x \\
\Large(\sec)'=\sec x\tan x\\
\Large(\csc x)'=-\csc x\cot x\\
\Large(a^x)'=a^x\ln{}{a}\\
\Large(\log{a}{x})'=\frac{1}{x\ln{}{a}}\\
\Large(\arcsin x)'=\frac{1}{\sqrt{1-x^2}}\\
\Large(\arccos x)'=-\frac{1}{\sqrt{1-x^2}}\\
\Large(\arctan x)'=\frac{1}{1+x^2}\\
\Large(\operatorname{arccot}  x)'=-\frac{1}{1+x^2}\\
$$

## 单调性
$$
\Large 从f'(x)出发\\ 
\Large１.f'(x)=0\to 驻点\\
\Large２.导数不存在点　\\
$$

## 凸凹性

![image-20221212120551630](C:\Users\LD_moxeii\AppData\Roaming\Typora\typora-user-images\image-20221212120551630.png)

$$
\Large f''(x) 正\to凹\\
\Large f''(x) 负\to凸\\
$$
# 微分

$$
\Large\frac{\mathrm{d} y}{\mathrm{d} x} =\frac{1}{\frac{\partial y}{\partial x} } \\
\Large\mathrm{d}y=f'(x)\mathrm{d}x\\
\Large x\to0\\
\Large(1+x)^\alpha\approx1+\alpha x\\
\Large\sin x\approx x\\
\Large\tan x\approx x\\
\Large e^x\approx 1+x\\
\Large \ln{}{1+x}\approx x\\
$$

## 洛必达法则

### 适用范围

$$
\Large \frac{0}{0};\frac{\infty}{\infty};0·\infty;\infty-\infty;0^0;1^\infty;\infty^0
$$
都化为前两种基本形式

### 使用情况

$$
\Large 1 .当\lim  \frac{F'(x)}{f'(x)} 时
洛必达法则不适用\\
\Large 2. 一般需要连续求导\\
\Large 3. 求导后检查符合条件\\
\Large 4. 善用等价无穷小替换\\
\Large 5.外移常数或趋于常数的项\\
$$

### 当$\Large x\to \infty$

$\Large x <\ln{}{x}<\sqrt{x}<x^2$