---
title: '遥感实验：基于主成分分析的遥感图像模拟真彩色融合'
date: 2020-05-12 18:18:42
tags: [遥感,ERDAS]
published: true
hideInList: false
feature: https://i.loli.net/2020/05/12/zRO9svPkQwbjHca.png
isTop: false
---
**实验三 基于主成分分析的遥感图像模拟真彩色融合**

## **一、实验背景**

遥感图像的关键在于选择合适的融合方法，恰当的融合方法可以提高图像空间信息的同时，很好的保持多光谱影像的光谱特征，基于主成分变换法的模拟真彩色融合法不仅具有主成分分析融合法的光谱选择灵活和光谱信息损失小等优点，同时还可以获得逼真的自然色彩融合图像，提高图像的融合效果。

## **二、实验目的**

主成分分析首先将具有多波段的多光谱图像经过PCA变换为多个独立的主成分，通常第一主成分包含有多个波段共同和唯一的光谱信息；其次将具有高分辨率的全色影响经过灰度拉伸，使其灰度的均值与方差和PCA变换的第一主成分图像一致；最后以拉伸过的高分辨图像代替第一分量图像，经过主成分逆变换完成图像融合。

## **三、实验数据**

多光谱影像（多光谱.img）、全色影像（全色.img）

## **四、实验要求**

①主成分变换

②用全色影像代替第一主成分（首先进行直方图均衡化灰度值拉伸），实现数据融合

③主成分逆变换

④自然色彩变换

## **五、实验步骤**

### **（一）主成分变换**

1.选择Interpreter-Spectral Enhancement-Principal-Components命令，打开Principal
Components对话框。

![](https://blog.manchan.ml/post-images/68788931183f51e82236e1e5488cab53.png)

2.在Principal Components对话框进行进行如图所示设置。

![](https://blog.manchan.ml/post-images/cbf28beb387946a4316a9a9c61fcbc69.png)

3.单击OK按钮执行主成分变换。

![](https://blog.manchan.ml/post-images/4c1dc4f7d481e0c5c9dca56478717c74.png)

4.结果如下图

![](https://blog.manchan.ml/post-images/032f73b04587ad57e2a9cc35b4133866.png)

### **（二）用全色影像代替第一主成分，实现数据融合**

在执行代替之前，首先对全色影像进行拉伸处理，选择Main-Image
Interpreter-Radiometric Enhancement-Histogram Equalization命令，打开Histogram
Equalization对话框，在Histogram Equalization对话框中进行如下设置。

![](https://blog.manchan.ml/post-images/414358888dcfb12ac21d42e60d661a03.png)

![](https://blog.manchan.ml/post-images/b187f72ca24567e3db6a189770f37d72.png)

![](https://blog.manchan.ml/post-images/ccfa1778f5025b44f85ec212d73d4652.png)

![](https://blog.manchan.ml/post-images/610cd5da30066888216945285576ee25.png)

将执行过主成分变换的数据的第一主成分用经拉伸处理后的全色影像代替，其他主成分顺序不变；即通过Layer
Selection and
Stacking对话框，依次添加全色影像、第二成分、第三主成分、第四主成分，具体操作如下：

1.选择Interpreter-Utilities-Layer Stack命令，打开Layer Selection and
Stacking对话框。

![](https://blog.manchan.ml/post-images/62add25a9c70826a31b55521d203516e.png)

2.在Layer Selection and Stacking对话框进行如下设置。

![](https://blog.manchan.ml/post-images/d9fa0a5d3ff420c0484f5dc38c0afed2.png)

![](https://blog.manchan.ml/post-images/feb9e785ad21aa147ce906eec62e3db3.png)

3.结果如下图

![](https://blog.manchan.ml/post-images/0fa6be254d9855bee94e1e09647d3572.png)

### **（三）主成分逆变换**

通过执行主成分逆变换，完成全色影像与多光谱影像的融合，具体操作步骤如下：

1.选择Interpreter-Spectral Enhancement-Inverse
Principal-Components命令，打开Inverse Principal Components对话框。

![](https://blog.manchan.ml/post-images/2ea8d96185247df2a0bbc20990b5a4ef.png)

1. 在Inverse Principal Components对话框中进行如下设置。

![](https://blog.manchan.ml/post-images/01fe85730949887b706248d20a4a6f12.png)

![](https://blog.manchan.ml/post-images/392868f4297109c6877a575b28e577df.png)

3.单击OK按钮，执行主成分逆变换。变换后的结果如下所示：

![](https://blog.manchan.ml/post-images/5ed5eaa63275bcb30bcabcd41b77578e.png)

### **（四）自然色彩变换**

通过以上几步，得到了模拟真彩色的影像，通过自然彩色变换，对多波段数据进行交换运算，就能得到自然色彩图像，具体操作如下：

1.选择Interpreter-Spectral Enhancement-Natural Color命令，打开Natural
Color对话框。

![](https://blog.manchan.ml/post-images/b6391176cdc0fba731ce269176fd0a0c.png)

2. 在Natural Color对话框中进行如下设置。

![](https://blog.manchan.ml/post-images/bc8aab94cc505d42c42eec383692b4d3.png)

![](https://blog.manchan.ml/post-images/177b782c8585e2358578bdaa8b382a10.png)

3.单击OK按钮完成自然色彩变换。变换后的图像如下图所示：

![](https://blog.manchan.ml/post-images/86d38cb7fa7554bf540a6f163a68837d.png)

4.对比图：

![](https://blog.manchan.ml/post-images/be7ac4bdcc2b5c0e77f4100ba78690ad.png)

## **六、实验总结**

本实验学会了运用主成分变换方法，实现对不同空间分辨率、时间分辨率和波谱分辨率的遥感图像进行综合、高效利用，以提高图像的解译效果。练习了ERDAS的使用方法。