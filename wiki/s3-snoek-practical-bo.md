---
id: S3
title: Practical Bayesian Optimization of Machine Learning Algorithms
authors: Jasper Snoek, Hugo Larochelle, Ryan P. Adams
venue: NIPS 2012 (arXiv:1206.2944)
url: https://arxiv.org/abs/1206.2944
type: 一手（會議論文）
read_depth: 摘要與前言片段（含 §2 開頭）；實驗與演算法細節未讀
---

# S3　Practical Bayesian Optimization of Machine Learning Algorithms

## 一句話摘要
把機器學習的超參數調整視為黑箱最佳化，用 GP-BO 自動化；強調核函數與其超參數處理的重要性，並提出考慮實驗成本與平行運算的做法。

## 主張（僅摘要層級）
| ID | 主張 |
|---|---|
| C5.2 | 超參數調整常被視為需要專家經驗的「黑魔法」；作者將其放入 BO 框架，結果可達到或超過人類專家水準（LDA、structured SVM、卷積網路）。 |
| C2.5 | GP 的核函數類型與其超參數的處理，對能否得到好的最佳化器有關鍵影響。 |
| C5.2′ | 另提出考慮實驗耗時（成本）的演算法，以及能利用多核心平行實驗的演算法。 |
| C1.4 | 此文使 BO 用於訓練深度網路受到關注（由 S2 引用說明）。 |

## 警示
- **O4：** NeurIPS 頁面用語為「reach or surpass」，arXiv 版為「exceed」。→ 簡報採保守的「達到或超過」。
- **O2：** 本文以最小化寫（找 f 的最小值）。
- **讀取深度不足：** 具體演算法（成本感知、平行化）、實驗設定與數據均未讀，不得引用細節。

## 連結
- 概念：[C2](index.md#c2) [C5](index.md#c5)
- 相關：S1（實例）、S2（歷史脈絡）
