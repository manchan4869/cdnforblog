---
title: 'ERDAS 9.2安装教程'
date: 2020-05-12 12:38:02
tags: [遥感,ERDAS]
published: true
hideInList: false
feature: https://i.loli.net/2020/05/12/zRO9svPkQwbjHca.png
isTop: false
---
以下内容针对64位系统下ERDAS 9.2的安装

<!-- more -->

## 1.下载软件
```
百度云下载地址：https://pan.baidu.com/s/12Ax9vl_bifslzLHE5nkR9Q 提取码：oxch

备用下载地址：https://pan.baidu.com/s/1UsJRj137Ti_iTPWr3df9DA
```
## 2.修改许可证

用记事本等纯文字编辑软件打开```erdas9.2\ERDAS9.1_Crack\ERDAS9.1_Crack\Crack```文件夹中license.dat，将首行SERVER $\color{red}{DESKTOP-0V5IM9B}$  ANY中红字部分改为自己计算机名并保存。

计算机名在此电脑-属性中寻找（以Win10为例）
![计算机名](https://i.loli.net/2020/05/12/Qekgxra897LcH25.png)
修改后为
![修改后](https://i.loli.net/2020/05/12/ta6iLJZ5TvPWeGR.png)



## 3.安装ERDAS

在文件夹erdas9.2\IMAGINE_9.2中打开安装包，双击运行setup.exe

![ERDAS安装1](https://i.loli.net/2020/05/12/QWxaNgUTDbMk3zZ.png)

同意条款

![ERDAS安装2](https://i.loli.net/2020/05/12/ZGhtu7eJAnpkE32.png)

改安装地址，自行修改

![ERDAS安装3](https://i.loli.net/2020/05/12/dhWvFgwxaJ9cyEN.png)

之后一直默认就好，最后点“Finish”，至此安装完毕

## 4.替换许可证

将```erdas9.2\ERDAS9.1_Crack\ERDAS9.1_Crack\Crack```文件夹中ERDAS.exe和license.dat复制到安装目录下替换掉同名文件

如果你跟我一样是64位系统，这里的安装目录指的是

```C:\Program Files (x86)\Leica Geosystems\Shared\bin\ntx86```

这个软件内的部分32位程序默认会放在这里，上面自定义的安装位置存放的是它的64位程序

![替换许可证](https://i.loli.net/2020/05/12/tGjmPELMqSYhfQo.png)

## 5.配置许可证服务

1现在对license进行设置，开始菜单>FLEXlm Tool>config service栏进行如下设置，下面不打勾（以免装arcgis、envi时许可管理冲突）；

![FLEXlm Tools](https://i.loli.net/2020/05/12/bTMKmYotJV7vfw8.png)

![](https://i.loli.net/2020/05/12/JWS5ZQ6gdyB3zHj.png)

具体为：
```
C:\Program Files(x86)\Leica Geosystems\Shared\bin\ntx86\lmgrd.exe

C:\Program Files(86)\LeicaGeosystems\Shared\bin\ntx86\license.dat

C:\Program Files(86)\LeicaGeosystems\Shared\bin\ntx86\erdas.log（这个是自己新建的 新建一个.txt文档然后改成.log）
```
![](https://i.loli.net/2020/05/12/rTey1z9U4puMGOS.png)

![](https://i.loli.net/2020/05/12/TtsSz7Bv1D2FJOm.png)

![](https://i.loli.net/2020/05/12/jKiSE3zkTeNDxLg.png)

## 6.运行许可证服务

再到start/stop/reread栏点start server,出现successful,表示成功了.

![](https://i.loli.net/2020/05/12/ktIpdvqhi8OWbu9.png)

现在打开erdas软件，如跳出对话框，则点选第一栏，在后面输入localhost，就可以使用了

![](https://i.loli.net/2020/05/12/3NWUyL7O1dkRwfh.png)

## 7.其他

打开时会弹出Viewer样式选择

![](https://i.loli.net/2020/05/12/RuycZKk6a7YLV1J.png)

第一种

![](https://i.loli.net/2020/05/12/RSeKqI4rJcQB6Gg.png)

第二种

![](https://i.loli.net/2020/05/12/bBxh6CnastMzgJR.png)

退出时会询问是否打印日志，没有打印机的话可以直接关掉这个提醒

![](https://i.loli.net/2020/05/12/NpJkZ8ceAzGD1d9.png)