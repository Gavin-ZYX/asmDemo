# 【Android】函数插桩（Gradle + ASM）

![图片来自google](https://upload-images.jianshu.io/upload_images/1638147-0de01f1709f62a14.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 前言
第一次看到插桩，是在[Android开发高手课](https://time.geekbang.org/column/142)中。看完去查了一下：“咦！**还有这东西，有点意思**”。
![](https://upload-images.jianshu.io/upload_images/1638147-4f6c729907f1b4cd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

本着不断学习和探索的精神，便走上学习函数插桩的“**不归路**”。

## 函数插桩

### 是什么函数插桩
**插桩**：目标程序代码中某些位置**插入或修改**成一些代码，从而在目标程序运行过程中获取某些程序状态并加以分析。简单来说就是**在代码中插入代码**。
那么**函数插桩**，便是在函数中插入或修改代码。

本文将介绍**在Android编译过程中，往字节码里插入自定义的字节码**，所以也可以称为**字节码插桩**。


### 作用
函数插桩可以帮助我们实现很多手术刀式的代码设计，如**无埋点统计上报、轻量级AOP**等。
应用到在**Android**中，可以用来做用行为统计、方法耗时统计等功能。