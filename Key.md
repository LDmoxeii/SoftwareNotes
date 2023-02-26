[TOC]



## Vim

### ScrollOff 参数

```
:set so=5-->可以令屏幕滚动时在光标上下方保留5行预览代码
```
### 行号定位


```
普通模式下输入 行号G 或 :行号<回车> 都能快速定位到某一行。
```
### 进入修改
```
o - 在当前行下方插入新行并自动缩进
O - 在当前行上方插入新行并自动缩进
i - 在当前字符左方开始插入字符
a - 在当前字符右方开始插入字符
I - 光标移动到行首并进入插入模式
A - 光标移动到行尾并进入插入模式
s - 删除光标所在字符并进入插入模式
S - 删除光标所在行并进入插入模式
r - 修改光标所在字符，然后返回普通模式
R - 进入覆盖模式
```
### 范围操作
```
d<范围> - 删除一定范围内的文本
c<范围> - 删除一定范围内的文本并进入插入模式
y<范围> - 将范围内的文本放入0号和"号注册栏
v<范围> - 选择范围内的文本
=<范围> - 自动缩进范围内的文本
gU<范围> - 将范围内的字符转换为大写
gu<范围> - 将范围内的字符转换为小写
\><范围> - 将范围中的内容缩进一格
<<范围> - 将范围中的内容取消缩进一格
```
#### 常用的范围指令

```
空格 - 光标所在位置字符。（例如 gU空格 - 将光标位置字符转为大写）
$ - 从光标位置到行尾
^ - 从光标位置到行首，不包含缩进空白
0 - 从光标位置到行首，包含缩进空白
gg - 从光标位置到文件开头
G - 从光标位置到文件结尾
% - 从光标位置到另一边匹配的括号
aw - 一个单词加一个空格 （a可理解为“一个”，下同）
iw - 一个单词 
a" - 一个字符串包括双引号
i" - 一个字符串内部文本
a< - 一组< >包含的文本，包括< >号本身-->同理类推： i<, a[, i[, a(, i(
用/或?命令查找时，正则表达式默认大小写敏感，如果需要不敏感，可以在正则表达式开始处加上\c标志。
```

### 选择文本


```
v - 进入字符选择模式
V - 进入行选择模式
Ctrl+v - 进入块选择模式
进入相应模式后移动光标即可选中文本。过程中可按o键令光标在选区两端切换。
```

### 一些常用组合技

```
全选： ggvG
调换两个字符位置： xp
复制一行： yyp
调换两行位置： ddp
插入模式下到行尾继续输入（相当于End键）： Ctrl+o A 或 Ctrl+[ A
插入模式下到行首继续输入（相当于Home键）： Ctrl+o I 或 Ctrl+[ I
到类定义位置（适用于正确缩进的public，protected类） ： ?^p回车
```

### 一些插入模式下的常用快捷键

|  快捷键  |                   中文解释                   |
| :------: | :------------------------------------------: |
|  Ctrl+h  |               删除光标左边字符               |
|  Ctrl+w  |              删除光标左边的单词              |
|  Ctrl+y  |              复制上方的一个字符              |
|  Ctrl+e  |              复制下方的一个字符              |
| Ctrl+r 0 |         插入前一次用y命令寄存的内容          |
| Ctrl+r * |             插入系统剪贴板的内容             |
|  Ctrl+a  |        插入前一次插入模式所键入的内容        |
|  Ctrl+o  |   执行一个普通模式下的命令然后返回插入模式   |
|  Ctrl+c  | 执行一个大写普通模式下的命令然后返回插入模式 |
|          |                   删除缩进                   |
|  ctel+h  |               删除光标前的字符               |
|  ctrl+i  |                    ==tab                     |
|  ctrl+t  |                   添加缩进                   |
|  ctrl+u  |                 删除光标之前                 |

<div style="page-break-after: always;"></div>

## IDEA

### 快速查找

| 快捷键           | 中文解释 | 英文           |
| ---------------- | -------- | -------------- |
| Ctrl+N           | 查找类   | Class          |
| Ctrl+Shift+N     | 查找文件 | File           |
| Ctrl+Shift+Alt+N | 查找符号 | Symbols        |
| ctrl+shift+A     | 查找动作 | Find in Action |
| ctrl+shift+F     | 全局查找 | Find in Path   |

### 快速跳转

| 快捷键               | 中文描述                 | 英文描述                |
| -------------------- | ------------------------ | ----------------------- |
| ctrl+G               | 跳转行/列                | Line/Column             |
| ctrl+alt+]           | 跳转下一个Project窗口    | next project window     |
| ctrl+shift+alt+]     | 跳转上一个Project窗口    | previous project window |
| ctrl+E               | 跳转最近打开的文件       | recent files            |
| ctrl+shift+Backspace | 跳转上一次修改的位置     | last edit location      |
| ctrl+alt+←           | 跳转上一次浏览的位置     | back                    |
| ctrl+alt+→           | 撤销跳转上一次浏览的位置 | forward                 |

### 书签与收藏

| 快捷键            | 中文描述                          | 英文描述                       |
| ----------------- | --------------------------------- | ------------------------------ |
| F11               | 定义书签                          | Toggle bookmarks               |
| shift+F11         | 显示书签列表                      | Show bookmarks                 |
| ctrl+shift+数字键 | 定义数字书签                      | Toggle bookmarks with Mnemonic |
| ctrl+数字键       | 跳转到指定的数字书签              | Go to Bookmark $num            |
| alt+shift+F       | 加入收藏                          | Add to Favorites               |
| alt+2             | 显示收藏窗口 包括书签、收藏、断点 | Favorites                      |

### 快速重构

| 快捷键     | 中文描述       | 英文描述  |
| ---------- | -------------- | --------- |
| shift+F6   | 重命名         | Rename    |
| ctrl+alt+V | 抽取为局部变量 | Variable  |
| ctrl+alt+C | 抽取为静态变量 | Constant  |
| ctrl+alt+F | 抽取为成员变量 | Field     |
| ctrl+alt+P | 抽取为形参     | Parameter |
|            | 抽取为方法     | Method    |

### 快捷Debug

| 快捷键        | 中文描述              | 英文描述               |
| ------------- | --------------------- | ---------------------- |
| F7            | 单步运行 进入方法体   | Step Into              |
| F8            | 单步运行 不进入方法体 | Step Over              |
| alt+F9        | 运行到光标            | Run to Cursor          |
| F9            | 运行到下一个断点      | Resume                 |
| ctrl+F8       | 添加普通断点          | Toggle Line Breakpoint |
| ctrl+shift+F8 | 查看/编辑断点         | View Breakpoints       |
| F2            | 修改变量值            | Set Value              |
| alt+F8        | 运行表达式求值        | Evaluate Expression    |

### 快捷操作

| 快捷键       | 中文描述       | 英文描述          |
| ------------ | -------------- | ----------------- |
| ctrl+D       | 删除行         | Delete            |
| ctrl+X       | 复制行         | Duplicate Line    |
| alt+ins      | 快捷生成代码   | Generate          |
| ctrl+alt+L   | 格式化代码     | Reformat Code     |
| ctrl+alt+T   | 快捷生成语法   | Surround With     |
| ctrl+O       | 覆盖父类方法   | Override Methods  |
| ctrl+I       | 实现父类方法   | Implement Methods |
| ctrl+7       | 查看类属性列表 | Structure         |
| ctrl+shift+U | 大小写转换     | Toggle Case       |
