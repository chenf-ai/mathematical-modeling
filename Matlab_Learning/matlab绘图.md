### 基本plot绘图

+ 基本plot绘图首先设置好X和Y变量的值，然后将X和Y作为plot的参数绘图，例如下例：

  ```matlab
  x = [0:0.01:10];
  y = sin(x);
  plot(x,y), xlabel('x'), ylabel('sin(x)'), title('sin(x) Graph'),
  grid on, axis equal;
  ```

+ 相关命令解析

  > xlabel, ylabel：设置x坐标和y坐标轴的标签
  >
  > title：设置图像标题
  >
  > grid on：设置网格线
  >
  > axis equal：设置坐标轴单位长度的实际长度相同（会影响图像的宽瘦）
  >
  > legend：设置线条的含义标签，如果有多个线条则legend可以有多个参数。

+ 设置线条样式

  具体样式的对应字符只需要在窗口中打印edit plot即可看到系统介绍文件。

  使用方法例如下面：

  ```matlab
  plot(x, y, x, g, 'r')	% 第一个线条是基本样式，第二个线条为红色
  plot(x, y, 'r', x, g, 'g')	% 两个线条分别为红色和绿色
  ```

+ 设置轴刻度

  ```matlab
  axis([xmin xmax ymin ymax])
  ```

  通过该代码分别设置x轴和y轴的最小、最大值。

+ 绘制子图

  ```matlab
  subplot(m, n, p)	% 例如subplot(1, 2, 2)
  					% 参照python matplotlib库用法理解
  ```

  其中m和n分别为积阵列的行和列的数量，p为指定子图的位置。

  具体用法是用在plot命令之前，相当于提前告知下面这个绘图的具体子图特征。

### 相关其他绘制

> bar：绘制柱状图
>
> contour：绘制等高线图（注意对meshgrid函数的理解）
>
> surf：绘制3-D图