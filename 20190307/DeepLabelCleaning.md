# Learning From Noisy Large-Scale Datasets With Minimal Supervision

CVPR 2017

## Poblem Definition

- Multi-label image classification
- 資料：標籤部分大部分有雜訊，少部分是乾淨的。

## Method

比起之前分開 Train 的方式（先用大 Dataset Train，再用小 Dataset Fine-Tune），這篇「一起」考慮了這兩種 Dataset。

主要是有三個 Net:

- 負責生圖片的 Feature: 圖 → Feature
- 在訓練時才會出現，負責把 Noise tags 轉成 Clean tags: (Feature, Noise tags) → Clean tags
- 從 Feature 到 Clean tags: Feature → Clean tags

### 針對不同種 Data 訓練

| Clean Tags                           | Noise Tags                           |
| ------------------------------------ | ------------------------------------ |
| ![](https://i.imgur.com/shjmSoh.png) | ![](https://i.imgur.com/G9SdfVe.png) |
