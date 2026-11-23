# Wiki Index：Bayesian Optimization

> 這是整個 Wiki 的入口。每次 ingest 後更新。規則見上層的 `AGENTS.md`（待建立）。

## 1. 來源頁（5 篇，皆為一手）

| ID | 頁面 | 作者／年份 | 讀取深度 | 狀態 |
|---|---|---|---|---|
| S1 | [s1-exploring-bayesopt.md](s1-exploring-bayesopt.md) | Agnihotri & Batra, 2020 | 全文 | ✅ |
| S2 | [s2-frazier-tutorial.md](s2-frazier-tutorial.md) | Frazier, 2018 | §1–3、§4.1 開頭 | ⚠️ 部分 |
| S3 | [s3-snoek-practical-bo.md](s3-snoek-practical-bo.md) | Snoek et al., 2012 | 摘要與前言 | ⚠️ 薄弱 |
| S4 | [s4-malu-high-dim-survey.md](s4-malu-high-dim-survey.md) | Malu et al. | 全文 | ✅ |
| S5 | [s5-foldager-uncertainty.md](s5-foldager-uncertainty.md) | Foldager et al., 2023 | 摘要開頭 | ⚠️ 薄弱 |

對應原始檔放在 `../sources/`（PDF 由使用者自行下載）。

## 2. 概念地圖（主張編號 → 出處）

<a id="c1"></a>
### C1 問題設定
昂貴、黑箱、無導數、約 20 維以下的連續空間，找全域最佳。比喻：挖金礦；與 active learning 的差別。
→ **S2**（C1.1、C1.4）、**S1**（C1.2–C1.3）、S4（C1.1′）

<a id="c2"></a>
### C2 代理模型（Gaussian process）
先驗 → 後驗；平均＋不確定性；核函數與超參數估計。
→ **S2**（C2.1–C2.4）、S1（C2.1）、S3（C2.5）

<a id="c3"></a>
### C3 Acquisition function
PI、EI、UCB、Thompson sampling；探索 vs 利用。
→ **S1**（C3.1–C3.3、C3.5–C3.8）、**S2**（C3.1、C3.3–C3.4）、S4（C3.5）、S5（C6.6 相關）

<a id="c4"></a>
### C4 BO 迴圈
先初始設計 → 更新後驗 → 最大化 acquisition → 評估 → 重複；回傳解的兩種做法。
→ **S2**（C4.1–C4.2）、S1（C4.1、C4.3）、S4（C4.1）

<a id="c5"></a>
### C5 機器學習應用
超參數調整；格子搜尋 vs BO 的例子；其他領域應用；常見工具。
→ **S1**（C5.1、C5.3、C5.5）、**S3**（C5.2）、S2（C5.4）、S4（C5.4）

<a id="c6"></a>
### C6 限制與注意事項
維度、計算成本、非凸的 acquisition 最大化、模型假設與核函數敏感度、高維對策。
→ **S4**（C6.1–C6.3）、**S1**（C6.4–C6.5）、S2（C6.1）、S5（C6.6）

## 3. 簡報對應（slides/bayesopt-deck.html）

| 頁 | 主題 | Wiki 主張 |
|---|---|---|
| 1 | 封面 | — |
| 2 | 昂貴的黑箱函數 | C1.1 |
| 3 | 挖金礦比喻 | C1.2–C1.3 |
| 4 | BO 的兩個零件 | C2.1、C3.1、C4.3 |
| 5 | 代理模型 | C2.2–C2.3 |
| 6 | 探索 vs 利用 | C3.2–C3.6 |
| 7 | 完整迴圈 | C4.1–C4.2、C3.1 |
| 8 | 超參數調整 | C5.1–C5.3 |
| 9 | 限制 | C6.1–C6.5 |
| 10 | 回顧與來源 | C1–C6 |

## 4. 待處理（Open）

| ID | 問題 | 處理 |
|---|---|---|
| O1 | S1 內部不一致：Matern 5/2 偏好「二次可微」vs Further Reading 說「一次可微」 | 簡報不寫幾次可微 |
| O2 | S2 用最大化、S3 用最小化 | 簡報統一最大化，視為對 f 取負 |
| O3 | S1 提到 Uber、Facebook、Netflix 的使用，屬演講轉述 | 未驗證，排除 |
| O4 | S3 摘要用語「reach or surpass」vs「exceed」 | 採「達到或超過」 |
| O5 | S2 §4.2 以後、S3 全文、S5 全文未讀 | 之後補讀；不引用細節 |

## 5. Lint 紀錄

| # | 檢查 | 結果 |
|---|---|---|
| 1 | 每則主張是否有來源 ID | 通過 |
| 2 | 簡報每頁是否能對回 Wiki 主張 | 通過（見上表第 3 節） |
| 3 | 跨來源一致性：d ≤ 20（S2 vs S4） | 一致 |
| 4 | 跨來源一致性：UCB 寫法（S1 λ、S4 β^½） | 一致（係數名稱不同） |
| 5 | 跨來源一致性：GP 計算成本（S4 O(N³) vs S1 Further Reading） | 一致 |
| 6 | 算術：C5.3 5×2×7＝70；70×15 分鐘 ≈ 17.5 小時 | 通過 |
| 7 | 來源內部一致性 | 發現 O1 |
| 8 | 讀取深度足夠？ | S3、S5 不足（O5） |
| 9 | 孤兒頁／缺連結 | 無（所有來源頁皆連回 index） |

## 6. Ingest 紀錄

| # | 動作 | 影響頁面 |
|---|---|---|
| 1 | ingest S1 | s1、C1、C3、C5、C6 |
| 2 | ingest S2 | s2、C1、C2、C3、C4 |
| 3 | ingest S3 | s3、C2.5、C5.2 |
| 4 | ingest S4 | s4、C6.2–C6.3 |
| 5 | ingest S5 | s5、C6.6（證據薄弱） |
