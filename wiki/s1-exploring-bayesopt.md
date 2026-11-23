---
id: S1
title: Exploring Bayesian Optimization
authors: Apoorv Agnihotri, Nipun Batra
venue: Distill, 2020-05-05 (DOI 10.23915/distill.00026)
url: https://distill.pub/2020/bayesian-optimization
type: 一手（互動式教學文章）
read_depth: 全文
---

# S1　Exploring Bayesian Optimization

## 一句話摘要
用「挖金礦」的比喻，從 active learning 一路帶到 BO：代理模型加 acquisition function，如何在探索與利用間取捨，最後用超參數調整當實例。

## 主張（可被簡報引用）
| ID | 主張 |
|---|---|
| C1.2 | 比喻：鑽探很貴，要用很少次鑽探找到金含量最高的位置。 |
| C1.3 | Active learning 要估準整張分布，所以挑最不確定的點；BO 只在乎最大值，所以要平衡探索與利用。 |
| C2.1 | 流程是先設代理模型的先驗，有觀測後用貝氏規則得到後驗。 |
| C3.1 | Acquisition function 是後驗的函數，衡量「在此評估有多值得」，本身便宜，要被最大化。 |
| C3.2 | PI：選超過目前最佳值（加 ε）機率最大的點；ε 控制探索，過大會探索過頭而近似 active learning。 |
| C3.3 | EI：同時考慮「會不會改善」與「改善多少」；平均高或不確定性高都會使 EI 變大。 |
| C3.5 | UCB：平均與不確定性的線性組合，係數調整探索與利用的偏好。 |
| C3.6 | Thompson sampling：從後驗抽一條函數，到它的高點去評估。 |
| C3.7 | 隨機選點在一維例子不差，但文中指出維度變多可能變差。 |
| C3.8 | 一維玩具例子中，多數 acquisition function 約 3 次評估就接近最大值，隨機法進步較慢（僅限該例）。 |
| C4.1 | 四步驟：選代理模型與先驗 → 由觀測得後驗 → 用 acquisition function 選下一點 → 加入資料後重複。 |
| C4.3 | 「Bayesian」是指每步都維護對 f 的估計與不確定性並用貝氏規則更新。 |
| C5.1 | 超參數調整是最常見用途；評估很貴時格子搜尋不可行，且隨超參數數量擴張很差。 |
| C5.3 | 神經網路例子：格子約 5×2×7＝70 次評估，BO 用 7 次；每次約 15 分鐘，格子約 17 小時。（算術已核對） |
| C5.5 | 列出常見工具：scikit-optimize、hyperopt、BoTorch、GPyOpt、Dragonfly 等。 |
| C6.4 | 隨機森林例子函數不平滑，各 acquisition function 都吃力，但仍勝過隨機法；說明 BO 效果取決於代理模型貼不貼近函數。 |
| C6.5 | 實務提醒：輸出尺度從 [0,1] 放大到 [0,100] 曾使其 GP 失靈，因為相關超參數需跟著縮放；GP 型 BO 對核函數敏感。 |

## 警示
- **O1（內部不一致）：** 正文說 Matern 5/2 偏好二次可微函數，Further Reading 卻說 Matern 核隱含一次可微。→ 不引用「幾次可微」。
- **O3（二手轉述）：** Further Reading 提到 Uber、Facebook、Netflix 等使用 BO，來源是演講轉述。→ 未驗證，排除。
- 文中公式（PI、EI、UCB）寫法完整，但簡報不放公式。

## 連結
- 概念：[C1](index.md#c1) [C2](index.md#c2) [C3](index.md#c3) [C4](index.md#c4) [C5](index.md#c5) [C6](index.md#c6)
- 相關：S2（形式化定義）、S4（高維限制）
