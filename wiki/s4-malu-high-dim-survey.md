---
id: S4
title: Bayesian Optimization in High-Dimensional Spaces: A Brief Survey
authors: Mohit Malu, Gautam Dasarathy, Andreas Spanias
venue: ASU SenSIP Center（NSF PAR 公開稿）
url: https://par.nsf.gov/servlets/purl/10274342
type: 一手（綜述）
read_depth: 全文（參考文獻僅略讀）
---

# S4　BO in High-Dimensional Spaces: A Brief Survey

## 一句話摘要
簡述標準 BO，說明為何維度一高 BO 就變困難，並整理利用目標函數結構來擴展到高維的方法與應用。

## 主張
| ID | 主張 |
|---|---|
| C1.1′ | 目標是優化昂貴的黑箱 f；定義域通常 D ≤ 20（與 S2 一致）。 |
| C3.5 | UCB 寫成 μₙ(x) + β^½·σₙ(x)；β 控制探索（高變異）與利用（高平均）的取捨。 |
| C4.1 | Algorithm 1：設先驗 → 觀測 → 重複（算後驗、算 acquisition、取最大化點、觀測、加入資料）→ 回傳觀測值最大的點。 |
| C5.4 | 應用：超參數調整、電路設計、機器人步態、化學與藥物設計、基因設計等。 |
| C6.1 | BO 在中低維成功，但高維有挑戰。 |
| C6.2 | 高維三大困難：①覆蓋空間所需評估數隨維度指數成長；②後驗需核矩陣反運算，約 O(N³)；③最大化 acquisition function 是非凸問題，成本隨維度快速上升。另有非參數迴歸的維度詛咒。 |
| C6.3 | 對策：假設有效維度很低（如 REMBO、ALEBO）、假設加成結構（如 ADD-GP-UCB），或以收斂速度換計算量（如 dropout 式方法）。 |

## 警示
- 本文為綜述，演算法細節（REMBO、ADD-GP-UCB 等）只作概念引用，不複述推導。
- 部分數字（如 O(N³)）為作者對標準 GP 的說明，與 S1 Further Reading 提到的「隨觀測數三次方擴張」一致。

## 連結
- 概念：[C3](index.md#c3) [C4](index.md#c4) [C6](index.md#c6)
- 相關：S2（d ≤ 20 的出處）、S1（模型假設不合時的例子）
