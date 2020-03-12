# MATLAB的基本学习

### MATLAB特性

> MATLAB属于解释型的语言工具。

### MATLAB中运算符的使用

> **+**   :	加；加法运算符；矩阵加法是按位进行加减法
>
> **-**    :	减；减法运算符
>
> *****   :	标量和**矩阵乘法**运算符号
>
> **.***	:	数组乘法运算符
>
> **^**    :	标量和矩阵求幂运算符
>
> **.^**   :	数组求幂运算符
>
> **\\**     :	矩阵左除
>
> **/**     :	矩阵右除
>
> **.\\**    :	阵列左除
>
> **./**    :	阵列右除
>
> **:**     :	向量生成；子阵提取
>
> **( )**   :	下标运算；参数定义
>
> **[ ]**   :	矩阵生成
>
> **.**      :	点乘运算，常与其他运算符联合使用
>
> **...**    :	续行标志；行连续运算符
>
> **,**      :	分行符（该行结果显示）
>
> **;**      :	语句结束；分行符（该行结果不显示）
>
> **%**    :	注释标志
>
> **_**      :	引用符号和转置运算符
>
> **._**     :    非共轭转置运算符
>
> **=**      :	赋值运算符

### MATLAB特殊符号和变量

> **ans**	:	最近一次运算结果
>
> **eps**	:	浮点数的相对误差
>
> **i, j**	:	虚数单位
>
> **Inf**	:	无穷大
>
> **NaN**	:	不是数字
>
> **pi**	:	圆周率$\pi$

### 关于矩阵

> A'：求矩阵A的转置
>
> inv(A)：求矩阵A的逆矩阵
>
> det(A)：求矩阵的行列式
>
> dot(a, b)：求内积

### 保存读取工作进度

> save	workloadfile

保存为扩展名为.mat的文件到当前工作区，实际保存的是所有的变量值；可使用load加载。

> load	workloadfile

### 查看变量

	who

返回结果样例为

	Your variables are:
	a	ans	 b	c	x	y
此外还有whos命令，其显示内容还包括：

+ 当前内存中的变量
+ 每个变量的类型
+ 内存分配给每个变量
+ 无论他们是复杂的变量与否

返回结果样例为

	Name	Size	Bytes	Class	Attributes
	
	a		1x1		8		double
	ans		1x1		8		double
	b		1x1		8		double	
	c		1x1		8		double	
	x		1x1		8		double
	y		1x1		8		double
### 删除变量——clear命令

clear命令可用于从内存中删除指定变量，若不指定则删除所有变量。

### ...的使用

长任务可通过省略号(...)延伸到另一个线路，例如，
	initial_velocity = 0;
	acceleration = 9.8;
	time = 20;
	final_velocity = initial_vlocity ...
	          +acceleration * time

### MATLAB格式命令——format命令

+ 默认情况下格式为四个小数位值显示数字，这就是所谓的short format

+ 如果要改为长命令格式，则使用format long

+ 空格格式命令会变为小数点后两位数字，例如：

  ```Matlab
  format bank
  daily_wage = 177.45
  weekly_wage = daily_wage * 6
  ```

  MATLAB将执行上面的语句，并返回以下结果：

  ```matlab
  weekly_wage = 
  				1064.70
  ```

+ 短格式e命令允许以指数的形式显示小数点后四位，加上指数

  ```
  format short e
  ```

+ format rat命令会给出最接近的有理表达式，从计算所得，例如

  ```matlab
  format rat
  ```

+ MATLAB创建向量 

  ```matlab
  r = [7 8 9 10 11]	%结果为行向量，且结果会告知每一行的元素
  					%行向量也可以表示为[6, 8, 9, 10, 11]
  r = [7; 8; 9; 10; 11] %结果为列向量
  ```

+ MATLAB创建矩阵

  ```
  m = [1 2 3; 4 5 6; 7 8 9]
  ```

### MATLAB命令（即查即用，十分重要）

[MATLAB基本命令使用](https://www.w3cschool.cn/matlab/matlab-by7428gf.html)

**Statement**：笔记中包含相关链接，转载相关博客对MATLAB的介绍进行学习。

### 创建并运行脚本文件

+ 可以利用mkdir和chdir命令管理文件目录
+ 可以使用edit [filename]来开启编辑器模式
+ 跑脚本文件可以点击Run，也可以在命令行中输入>> prog1（不带扩展名 .m)

### MATLAB的基本数据类型

[MATLAB的基本数据类型](https://www.w3cschool.cn/matlab/matlab-ed7z28gh.html)

+ 注意char和int2str的区别

  ```matlab
  char(123)	%结果为'{'
  int2str(123)	%结果为'123'
  ```

### MATLAB运算符详解

[MATLAB运算符详解](https://www.w3cschool.cn/matlab/matlab-fms328gi.html)

### MATLAB中的函数

+ 函数一组语句一起执行任务；函数在自己的工作空间进行操作，被称为本地动作区，独立的工作区；函数可以接受多个输入参数和可能返回多个输出参数。

+ 函数实现

  + 创建单独的文件，文件名与函数名相同，例如如下的mymax.m文件，文件中代码为

    ```matlab
    function max = mymax(n1, n2, n3)
    %This function calculates the maximum of the
  % three numbers given as input
    max = n1;
    if (n2 > max)
        max = n2;
    end
    if (n3 > max)
        max = n3;
    end
    end
    ```
    
    在相同目录的交互式环境中使用help mymax，则会输出提示字符串（即注释内容）。
    
  + 匿名函数
  
    一般形式为
  
    ```matlab
    f = @(arglist)expression
    ```
  
    例如`power = @(x, n) x.^n;`即可快速定义幂次匿名函数。
  
  + 嵌套函数
  
    简单而言就是定义的函数里用到了sub-function，sub-function在之后定义。同时有将sub-funtion的定义嵌套写在function定义中的写法。
  
  + 对于函数的定义方式，可以利用全局变量；一般用大写方式写一个全局变量，然后在函数定义中使用该变量，那么在调用相关函数前，对相应的全局变量指定值即可。