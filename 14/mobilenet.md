# MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications

> Howard et al. MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications. arXiv 2017.

## Introduction

This paper proposed a compressing and accelerating method with trading of accuracy.

## Method

![](https://i.imgur.com/gVR4QdK.png)

### Basic

Replace **standard convolution filters** with combination of **depthwise convolution filters** and **pointwise convolution filters** and the time complexity can be reduce:

* Original Time Complexity: $D_K^2NMD_F^2$
* Modified Time Complexity: $(D_K^2 + N)MD_F^2$

![](https://i.imgur.com/l77oc6r.png)

## Result

|   Model   | ImageNet Accuracy | Mult-Add(Million) | Parameters(Million) |
| :-------: | ----------------- | ----------------- | ------------------- |
| MobileNet | 70%               | 569               | 4.2                 |
| GoogleNet | 69%               | 1550              | 6.8                 |
|   VGG16   | 71%               | 15300             | 138                 |