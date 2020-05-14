---
title: '遥感实验：DEM数据与遥感影像复合'
date: 2020-05-12 19:56:01
tags: [遥感,ERDAS]
published: true
hideInList: false
feature: https://i.loli.net/2020/05/12/zRO9svPkQwbjHca.png
isTop: false
---
**实验四 DEM数据与遥感影像复合**

## **一、实验背景**

非遥感数据与遥感数据复合是提高遥感影像解译精度的重要方法之一。彩色空间变换利用HIS（明度、色度和饱和度）色空间的特点，在信息融合方面取得了较好的效果。在遥感影像的处理中，它多用于多源影像的复合，将不同传感器获得的同一景物的影像或者是同一传感器获得的不同分辨率的影像经过色彩变换处理后，获得一幅合成影像，提高图像的解译能力。

## **二、实验目的**

熟练掌握ERDAS
IMAGINE彩色变换和信息融合技术，利用该方法实现非遥感数据与遥感数据复合，从而达到图像增强的目的。

## **三、实验数据**

TM影像（eldoatm.img）、DEM影像（eldodem.img）

## **四、实验要求**

（1）色彩变换

（2）用DEM数据替换IHS图像中的H分量。

（3）色彩逆变换，实现DEM数据与TM数据的融合。

## **五、实验步骤**

### **（一）色彩变换**

1.选择Interpreter-Spectral Enhancement-RGB to IHS…命令，打开RGB to IHS对话框。

![](https://blog.manchan.ml/post-images/c8a913abfd9eda928ad31292330226ec.png)

2.选择处理图像文件（Input File）为eldoatm.img

3.在Output File选择输出文件保存的路径和文件名（ihs.img）

4.Coordinate Type：坐标系统类型，选择Map

5.Subset Definition：定义变换区域整幅图像

6.确定参与色彩变换的3个波段

7.选中Ignore Zero in Stats复选框

![](https://blog.manchan.ml/post-images/479ab80dd7edc8cf1b7d8cb3cc6b8610.png)

1. 单击OK按钮，执行色彩变换。变换后的结果如下所示：

![](https://blog.manchan.ml/post-images/4431fbab61ed3c5599b2392bda440c49.png)

### **（二）用DEM数据替换IHS图像中的H分量**

由于明度I分量决定图像的空间分辨率，经常用在不同传感器影像的复合中，在变换中用高分辨率影像代替该分量，使得到的影像既具有较高的分辨率又具有丰富的光谱信息；S、H分量包含图像的光谱信息，本实验用DEM代替其色调H，以提高变换后的视觉效果。

由于H分量属于IHS图像的第二层，因此在利用Layer
Stack命令重新生成图层时，保持IHS图像的第1、3层不变，在两者中间插入DEM数据，即可实现DEM数据对IHS图像中H分量的替换。在替换之前，首先对DEM数据进行拉伸处理，操作步骤如下：

选择Main-Image Interpreter-Radiometric Enhancement-Histogram
Equalization命令，打开Histogram Equalization对话框，在Histogram
Equalization对话框中进行如下设置。点击OK按钮执行，结果如下：

![](https://blog.manchan.ml/post-images/142c7eb0e9bb5b7c41473753c6c34afd.png)

![](https://blog.manchan.ml/post-images/7f493047fca49a729fed0c7cb36d7929.png)

![](https://blog.manchan.ml/post-images/381f584fe8c21c7bcc84a5947b65daeb.png)

对原始DEM数据进行拉伸处理后，利用Layer
Stack命令，用拉伸后的DEM数据代替原始图像中的H分量，具体操作如下：

1.选择Interpreter-Utilities-Layer Stack命令，打开Layer Selection and
Stacking对话框。

![](https://blog.manchan.ml/post-images/c46fc6a68bfbfcd5149313193580b5b5.png)

2.选择要加载的文件。操作如下：首先打开IHS图像，在Layer中选择要加载的图层1，单击Add命令加载，作为I＇。然后打开equalizatiom.img文件，在Layer中选择图层1，单击Add命令加载，作为H＇。最后重新打开IHS图像，在Layer中选择要加载的图层3，单击Add命令加载，作为S＇。

3.在Output File中选择输出文件的路径和文件名（newihs.img）

4.选中Ignore Zero in Stats复选框

![](https://blog.manchan.ml/post-images/a8791a54f4689f96c951b49a45f3ce78.png)

5.单击OK按钮，执行Layer Stack命令。执行后结果如下所示：

![](https://blog.manchan.ml/post-images/1e10e48c6ca23c99edb1cbb6a95a074d.png)

### **（三）色彩逆变换**

1.打开IHS to RGB对话框；选择Interpreter-Spectral Enhancement-IHS to RGB命令。

![](https://blog.manchan.ml/post-images/4f52b0cc1e834ac020cd35d6b05e3b98.png)

2.选择处理图像文件（Input File）中选择在第二步中新生成的IHS图像。

3.在Output File选择输出文件保存的路径和文件名（newrgb.img）

4.选择Stretch I&S命令，对I、S两分量进行拉伸。

5.选中Ignore Zero in Stats复选框。

![](https://blog.manchan.ml/post-images/e0f6c793d215b31ee1aa3cd556fa7c99.png)

6.单击OK按钮，执行色彩逆变换，变换后的效果如下所示：

![](https://blog.manchan.ml/post-images/061d363fdb0500ad5b314a14fca08003.png)

7.对比图：

![](https://blog.manchan.ml/post-images/e5bae7d6daf32cf15e22c2c764d6e470.png)

## **六、实验总结**

通过该实验掌握了ERDAS的彩色变换和信息融合技术，利用该方法实现了非遥感数据与遥感数据复合，从而达到图像增强的目的。也更加熟练了ERDAS的用法。