## matlab求解代数基本使用

### solve命令

使用格式为

```matlab
solve(equation, variable)	% 例如solve('v-u-3*t^2=0','v')
```

下面给出进行二次方程求解的例子

```matlab
eq = 'x^2 -7*x + 12 = 0';
s = solve(eq);
disp('The first root is: '), disp(s(1));
disp('The second root is: '), disp(s(2));

% 运行结果如下
The first root is:
3
The second root is:
4
```

使用solve求解方程组问题

```matlab
s = solve('5*x + 9*y = 5','3*x - 6*y = 4');
s.x
s.y

% 运行结果为
ans = 
  22/19
ans = 
  -5/57
```

### roots命令

使用格式为

```matlab
roots(Coefficient list)
```

下面给出进性二次方程求解的例子

```matlab
s = roots([1, -7, 12]);

disp('The first root is: '), disp(s(1));
disp('The second root is: '), disp(s(2));

% 运行结果如下
The first root is:
4
The second root is:
3
```

### 除基本代数方程式求解外的纯数应用

+ 关于微积分：了解limits命令

  + limits用于求解极限，默认变量趋向于0，与syms配合使用

+ 关于多项式：了解polyval、polyvalm、poly命令

  + ```matlab
    %	对于polyval，求解特定多项式在某个赋值下的值
    p = [1, 7, 0, -5, 9]
    polyval(p,4)
    
    %	返回结果如下
    ans = 
    	693
    ```

  + poly命令可以看作是roots的逆命令，使用roots可以求解特定多项式方程的根，当给定一个根为参数时，可以使用poly命令求解对应的向量多项式表示（注意这样导致一个系数成比例问题，目前观察来看貌似是最高项系数为1）。


### 带参数变量的计算

+ 使用syms命令可声明符号变量，之后带有符号变量的计算会将其作为变量符号进行计算。

+ simplify命令可对带参数变量的计算结果进行简化。