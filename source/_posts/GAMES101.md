---
title: GAMES101
date: 2022-01-27 10:15:08
tags:
---

# 资源链接
[课程主页](https://sites.cs.ucsb.edu/~lingqi/teaching/games101.html)  
[B站视频](https://www.bilibili.com/video/BV1X7411F744)  
[latex公式生成](https://latex.codecogs.com/)

# Introduction
课程涉及4个部分：
光栅化、几何、光线追踪、模拟和动画

图形学依赖：
- 基础数学：线性代数、微积分、统计
- 基础物理：光学、力学
- 其他：信号处理、数值分析、美学

# Linear Algebra
向量（向量点乘、叉乘）和矩阵（矩阵的乘、矩阵和向量的乘）

## 向量
### 向量的点乘  
![](/images/vectex_dot_mult.png)

![](https://latex.codecogs.com/svg.image?\vec&space;a&space;\cdot&space;&space;\vec&space;b&space;=&space;||\vec&space;a||||\vec&space;b||&space;\cos\theta)

作用：通过乘积的符号判断两个向量的方向是否一致

### 向量的叉乘  
右手螺旋定则  
![](https://latex.codecogs.com/svg.image?\vec&space;a&space;\times&space;&space;&space;\vec&space;b&space;=&space;-\vec&space;a&space;\times&space;&space;\vec&space;b)
![](https://latex.codecogs.com/svg.image?||\vec&space;a&space;\times&space;&space;&space;\vec&space;b&space;||=&space;||\vec&space;a||||\vec&space;b||\sin\theta)

作用：通过乘积的符号判断向量在另一个向量的左侧还是右侧（点在区域内还是外）

# 变换

## 线性变换
![](https://latex.codecogs.com/svg.image?\begin{bmatrix}&space;&space;&space;&space;{x}'\\\\&space;&space;&space;&space;{y}'\end{bmatrix}&space;=&space;\begin{bmatrix}&space;&space;&space;&space;a&b\\\\&space;&space;&space;&space;c&d\end{bmatrix}&space;\begin{bmatrix}&space;&space;&space;&space;&space;&space;&space;&space;x\\\\&space;&space;&space;&space;y\end{bmatrix})
### 缩放
### 反射
![](https://latex.codecogs.com/svg.image?\begin{bmatrix}&space;&space;&space;&space;{x}'\\\\&space;&space;&space;&space;{y}'\end{bmatrix}&space;=&space;\begin{bmatrix}&space;&space;&space;&space;s_{x}&0\\\\&space;&space;&space;&space;0&s_{y}\end{bmatrix}&space;\begin{bmatrix}&space;&space;&space;&space;&space;&space;&space;&space;x\\\\&space;&space;&space;&space;y\end{bmatrix})

### 错切 shear 
![](/images/shear_matrix.png)

![](https://latex.codecogs.com/svg.image?\begin{bmatrix}&space;&space;&space;&space;{x}'\\\\&space;&space;&space;&space;{y}'\end{bmatrix}&space;=&space;\begin{bmatrix}&space;&space;&space;&space;1&a\\\\&space;&space;&space;&space;0&1\end{bmatrix}&space;\begin{bmatrix}&space;&space;&space;&space;&space;&space;&space;&space;x\\\\&space;&space;&space;&space;y\end{bmatrix})


### 旋转 rotate 
![](https://latex.codecogs.com/svg.image?\begin{bmatrix}&space;&space;&space;&space;{x}'\\\\&space;&space;&space;&space;{y}'\end{bmatrix}&space;=\begin{bmatrix}&space;&space;&space;&space;\cos\theta&space;&&space;-\sin\theta&space;\\\\&space;&space;&space;&space;\sin\theta&space;&&space;\cos\theta\end{bmatrix}\begin{bmatrix}&space;&space;&space;&space;x\\\\&space;&space;&space;&space;y\end{bmatrix}&space;)

## 齐次坐标
目的：统一表征平移变换

![](https://latex.codecogs.com/svg.image?\begin{bmatrix}&space;&space;&space;&space;{x}'\\\\&space;&space;&space;&space;{y}'\\\\&space;&space;&space;&space;{w}'\end{bmatrix}&space;=\begin{bmatrix}&space;&space;&space;&space;1&space;&&space;0&space;&&space;t_{x}\\\\&space;&space;&space;&space;0&space;&&space;1&space;&&space;t_{y}\\\\&space;&space;&space;&space;0&space;&&space;0&space;&&space;1\end{bmatrix}\begin{bmatrix}&space;&space;&space;&space;x\\\\&space;&space;&space;&space;y\\\\&space;&space;&space;&space;1\end{bmatrix}&space;=&space;\begin{bmatrix}&space;&space;&space;&space;x&plus;t_{x}\\\\&space;&space;&space;&space;y&plus;t_{y}\\\\&space;&space;&space;&space;1\end{bmatrix}&space;)

### 仿射变换 affine

![](https://latex.codecogs.com/svg.image?\begin{bmatrix}&space;&space;&space;&space;{x}'\\\\&space;&space;&space;&space;{y}'\\\\&space;&space;&space;&space;1\end{bmatrix}&space;=\begin{bmatrix}&space;&space;&space;&space;a&space;&&space;b&space;&&space;t_{x}\\\\&space;&space;&space;&space;c&space;&&space;d&space;&&space;t_{y}\\\\&space;&space;&space;&space;0&space;&&space;0&space;&&space;1\end{bmatrix}\begin{bmatrix}&space;&space;&space;&space;x\\\\&space;&space;&space;&space;y\\\\&space;&space;&space;&space;1\end{bmatrix}&space;)

### 逆变换

### 三维仿射变换

![](https://latex.codecogs.com/svg.image?\begin{bmatrix}&space;&space;&space;&space;{x}'\\\\&space;&space;&space;&space;{y}'\\\\&space;&space;&space;&space;{z}'\\\\&space;&space;&space;&space;1\end{bmatrix}&space;=\begin{bmatrix}&space;&space;&space;&space;a&space;&&space;b&space;&&space;c&&space;t_{x}\\\\&space;&space;&space;&space;d&space;&&space;e&f&space;&&space;t_{y}\\\\&space;&space;&space;&space;g&space;&&space;h&i&space;&&space;t_{z}\\\\&space;&space;&space;&space;0&space;&&space;0&space;&&space;0&1\end{bmatrix}\begin{bmatrix}&space;&space;&space;&space;x\\\\&space;&space;&space;&space;y\\\\&space;&space;&space;&space;z\\\\&space;&space;&space;&space;1\end{bmatrix})

## 三维旋转
旋转矩阵
![](/images/rotate_matrix.png)

罗德里格斯（Rodrigues）旋转方程
![](/images/Rodrigues.svg)

## 观测变换 Viewing Transformation
### 视图/相机变换 view/camera transformation
相机的位置 e  
相机朝向（gaze）的方向 g  
相机的向上方向 t  
![](/images/camera_trans.png)

不妨将相机和物体一同变换（保证相对位置不变），使得相机处在一个对后续投影变换处理方便的位置上（这是正是视图变换的目的），即：位于原点，看向-z轴，向上方向是y轴。

为了实现这个（刚体）变换，我们只需
- 将 e 平移到原点O
- 将 g 旋转到-z轴
- 将 t 旋转到y轴
![](/images/view_trans.jpg)

### 投影变换 projection transformation
正交投影出的图像不体现远近关系，而透视投影则是真实世界的反映。
![](/images/PerspectiveVsOrthographic.jpg)

#### 正交投影 Orthographic Projection
- 将中心移到原点
- 然后缩放，保证长宽高缩放到2
![](/images/perspective.png)
![](/images/orth_trans.svg)

#### 透视投影 Perspective Projection
![](/images/perspective.jpg)
- 挤压 squish
![](/images/squish.jpg)
![](/images/squish2.jpg)
那么我们可以得到
![](/images/persp_ortho.svg)
如何得到第三行的参数？
有以下两个前提推导：  
1. 在近平面（n）的点，z坐标不变
2. 在远平面（f）的点，z坐标不变
则由第一个前提，可得
![](/images/persp_ortho_1.jpg)
An+B = n*n  
Af+B = f*f  
最终得到
![](/images/persp_ortho_final.svg)

- 平移 正交投影（见上方）

### 课后思考题
Q: z坐标为(n+f)/2的点，经过透视投影后，z如何变化？
A：
![](/images/qa1.svg)
and
![](/images/qa1_2.svg)


