---
title: '遥感实验：几何校正'
date: 2020-05-11 18:39:22
tags: [遥感,ENVI]
published: true
hideInList: false
feature: https://i.loli.net/2020/05/11/WaqELB92d3GnO1H.png
isTop: false
---
## **一、实验背景**

引起图像几何变形一般分为两大类:系统性和非系统性。系统性一般由传感器本身引起，有规律可循和可预测性，可以用传感器模型来校正，卫星地面接收站已经完成这项工作;非系统性几何变形是不规律的，它可以是传感器平台本身的高度、姿态等不稳定，也可以是地球曲率及空气折射的变化以及地形的变化等。我们常说的几何校正就是消除这些非系统性几何变形。

## **二、实验目的**

1.利用地面控制点和几何校正数学模型来矫正非系统因素产生的误差，同时也是将图像投影到平面上，使其符合地图投影系统的过程;校正过程中会将坐标系统赋予图像数据，此过程包括了地理编码(geo-coding)。

2.学习使用ENVI Classic软件对遥感数据进行几何校正。

## **三、实验数据**

bldr_sp.img spot4 数据文件、bldr_tm.img TM 数据文件、ENVI Classic软件。

## **四、实验步骤**

1.打开ENVI Classic软件。

![](https://blog.manchan.ml/post-images/80650a48739ac0a0e76646aafa04436a.png)

2.选择File-Open Image File,将bldr_sp.img spot4 数据文件和bldr_tm.img TM
数据文件打开。

![](https://blog.manchan.ml/post-images/9c6ea2d8b483872c184bf2b9d025d860.png)

![](https://blog.manchan.ml/post-images/825d4a7dde77945973df084ef82ea683.png)

3.启动几何校正模块。依次点击Map-Registration-Select GCPs:Image to Image。

![](https://blog.manchan.ml/post-images/08f6b3012ff5fc3dab597bb55eb52ef0.png)

1. 选择显示SPOT文件的Display为基准图像（Base
   Image），显示TM文件的Display为待校正图像（Warp
   Image），点击OK按钮，进入采集地面控制点。

![](https://blog.manchan.ml/post-images/79996ea3c40c3c72de3ef57beee6f236.png)

![](https://blog.manchan.ml/post-images/090c21ed31a3852b60fa50f3aca7246e.png)

5.采集地面控制点，在两个图像中选取相同位置的点，在Ground Control Points
Selection上，单击Add Point按钮，将当前找到的点收集。

![](https://blog.manchan.ml/post-images/2ffab0c7fff2ddfa43ce557a487c64f3.png)

6.用同样的方法继续寻找其余的点，当选择控制点的数量达到3时，RMS被自动计算。Ground
Control Points
Selection上的Predict按钮可用，这时在基准图像显示窗口上面定位一个特征点，单击Predict
按钮，校正图像显示窗口上会自动预测区域，适当调整-一下位置，单击AddPoint按钮，将当前找到的点收集。随着控制点数量的增多，预测点的精度越来越精确。

![](https://blog.manchan.ml/post-images/f502cdc67ba0ef19f0b8224658c5e4aa.png)

7.选择Image to Image GCP List上的Options-Order Points by
Error,按照RMS值由高到低排序。对于RMS过高，可以是直接删除，选择此行，按Delete按钮;也可以在两个图像的窗口上，将十字光标重新定位到正确的位置，点击ImagetoImageGCP
List上的Update按钮进行微调。

![](https://blog.manchan.ml/post-images/dee0d2915d50fbc8afdd9b96bc25bc79.png)

![](https://blog.manchan.ml/post-images/112bf651607cdfb6018167b206e10799.png)

8.在Ground Control Points
Selection上，RMS值小于1个像素时，则表示点的数量足够且分布均匀，完成控制点的选择。

![](https://blog.manchan.ml/post-images/9c4ae69357efba1161305403989dfe56.png)

9.在Ground Control Points Selection上，选择File-Save GCPs to
ASCII,将控制点保存。

![](https://blog.manchan.ml/post-images/02af01dff17197abf5a1667c89de97b7.png)

![](https://blog.manchan.ml/post-images/71fa8bf9d63c7533b6bcf09738e2b709.png)

10.在Ground Control Points Selection上，依次点击Options-Warp File(as Image to
Map)，选择校正文件(TM文件)。

![](https://blog.manchan.ml/post-images/b131c4a0907eee856916ae32813820e1.png)

11.投影参数不变，在X和Y的像元大小输人30m,
按回车，图像输出大小自动更改。校正方法选择多项式(2次)。重采样选择Bilinear,设置背景值(Background)
为0。选择输出路径和文件名，单击OK按钮。得到校正后的图像。

![](https://blog.manchan.ml/post-images/5a7c9e49e37dd88d785115ccb037ed22.png)

![](https://blog.manchan.ml/post-images/15ce2b558928cd3c619e3aba1dedbeb1.png)

12.检验校正结果。在校正后的图像中依次点击Tools-Link-Geographic
Link，将所有的“off”改称“on”。就可以使用十字标进行对比查看。

![](https://blog.manchan.ml/post-images/2d9e92136746df8ea67f4858b5db0ba9.png)

![](https://blog.manchan.ml/post-images/be2b0777bfc932b6a6f228373d51e8d6.png)

## **五、实验总结**

通过这次实验我学会了使用ENVI软件进行对遥感图像的几何校正。实验中最麻烦的地方就是打地面控制点，为了精确需要打9个以上的地面控制点，而实验数据本身比较模糊，在打控制点的时候比较麻烦，很容易造成较大的误差。实验过程不复杂但是很需要耐心，相信通过这次实验已经大概了解了ENVI
Classic的简单操作。