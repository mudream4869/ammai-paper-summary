# ChestX-ray8: Hospital-scale Chest X-ray Database and Benchmarks on Weakly-Supervised Classification and Localization of Common Thorax Diseases

CVPR 2017

## Problem Definition

給定胸腔的 Xray 圖片，做出 8 種病徵分類。

- 原始資料是胸腔 X 光圖片和診斷描述，需要把診斷描述用 NLP 轉換成 Tag(s)。

## Method

![](https://i.imgur.com/avy2lp6.png)

主要結構如上圖， Image 會先送進 4 個 Pretrained 的 Net ，然後把 Output 合併，然後用 Pooling 後預測出的 Weight 做加權算出 Heat Maps。

### Loss

由於分類用的訓練資料在每種類別上並沒有很均勻，所以 Loss 有用數量來做加權。
