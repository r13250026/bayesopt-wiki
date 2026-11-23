---
id: S2
title: A Tutorial on Bayesian Optimization
authors: Peter I. Frazier
venue: arXiv:1807.02811, 2018-07
url: https://arxiv.org/abs/1807.02811
type: 一手（教學論文）
read_depth: 摘要、§1 引言、§2 概述、§3 GP 迴歸、§4.1 EI 開頭；§4.2 knowledge gradient 以後、§5 exotic BO、§6 軟體未讀
---

# S2　A Tutorial on Bayesian Optimization

## 一句話摘要
給出 BO 的正式問題設定（昂貴、黑箱、無導數、約 20 維以下）、基本演算法，並詳細介紹 GP 迴歸與 EI。

## 主張
| ID | 主張 |
|---|---|
| C1.1 | 問題：max f(x)。f 評估昂貴（常只能做幾百次）、無特殊結構（黑箱）、拿不到導數；x 通常為 d ≤ 20 的連續空間，目標是全域最佳。 |
| C1.4 | BO 在工程設計已用了很久（自 1960 年代）；Snoek 等人指出可用於訓練深度網路後，在 ML 界受到大量關注。 |
| C2.1 | BO 有兩個組件：貝氏統計模型（通常是 GP）與 acquisition function。 |
| C2.2 | GP 後驗在任一點是常態分佈（平均 μₙ、變異數 σₙ²）；平均穿過已觀測點，不確定區間在觀測點寬度為 0，離觀測點越遠越寬。 |
| C2.3 | 核函數使距離近的點有較高相關，編碼「函數值較相似」的假設。 |
| C2.4 | 先驗超參數的估計有三種：MLE、MAP、完全貝氏（以取樣近似）。 |
| C3.1 | Acquisition function 衡量在新點評估所帶來的價值，由當前後驗計算。 |
| C3.3 | EI 的定義：評估後「目前最佳觀測值」的預期改善量（取正部分的期望）。無噪音時，已評估點的 EI 為 0；不確定性大或平均高的點 EI 傾向較大。 |
| C3.4 | EI 是最常用的 acquisition function，效果好且易用。 |
| C4.1 | 演算法：設 GP 先驗 → 以空間填滿式初始設計（常為隨機）評估若干點 → 重複「更新後驗、最大化 acquisition、評估」直到預算用完。 |
| C4.2 | 回傳解：已評估點中觀測值最大者，或後驗平均最大者。 |
| C5.4 | 應用：實驗室實驗、藥物與材料設計、環境模型校準、強化學習等。 |
| C6.1 | 最適合約 20 維以下的連續空間，並可容忍評估噪音。 |

## 警示
- **O2：** 本文寫成最大化；S3 寫成最小化（等價於對 f 取負）。
- **O5：** §4.2 以後未讀，不引用 knowledge gradient、entropy search、噪音版 EI 的細節。
- 文中公式（GP 後驗、EI）本 Wiki 不轉錄。

## 連結
- 概念：[C1](index.md#c1) [C2](index.md#c2) [C3](index.md#c3) [C4](index.md#c4) [C6](index.md#c6)
- 相關：S1（直覺版）、S4（同樣寫 d ≤ 20，引用本文）
