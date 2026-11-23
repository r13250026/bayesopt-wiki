# Bayesian Optimization LLM Wiki

用 LLM Wiki 方法整理 **Bayesian Optimization（貝氏最佳化）** 的知識，並以這個 Wiki 作為唯一知識來源，製作一份 10 頁的教學型 HTML 簡報。

## 專案內容

Bayesian Optimization（BO）用來解「評估一次很貴、又拿不到導數的黑箱函數」最佳化問題，典型例子是每次訓練要數小時的超參數調整。核心是兩個零件：用 Gaussian process 估計函數的**代理模型**，以及決定下一個要試哪裡的 **acquisition function**（在探索與利用間取捨）。

## 資料夾結構

```
bayesopt-project/
├── README.md          # 本檔
├── AGENTS.md          # AI 維護 Wiki 的規範與自動化流程（含流程圖）
├── sources/           # 原始 PDF（5 篇，唯讀）
├── wiki/
│   ├── index.md       # 入口：來源表、概念地圖、簡報對應、Open、Lint／Ingest 紀錄
│   ├── s1-exploring-bayesopt.md
│   ├── s2-frazier-tutorial.md
│   ├── s3-snoek-practical-bo.md
│   ├── s4-malu-high-dim-survey.md
│   └── s5-foldager-uncertainty.md
└── index.html        # 10 頁教學簡報
```

## 如何瀏覽

- **簡報：** 用瀏覽器直接開啟 `index.html`。按 ← → 或空白鍵翻頁，也可點下方按鈕。支援深色模式與手機寬度。
- **Wiki：** 從 `wiki/index.md` 開始，依概念地圖（C1–C6）進入各來源頁。
- **流程：** 看 `AGENTS.md`，第 5 節有 mermaid 流程圖（需支援 mermaid 的環境，如 GitHub 或 VS Code 預覽）。

## 來源（5 篇，皆為一手）

| ID | 來源 |
|---|---|
| S1 | Agnihotri & Batra, *Exploring Bayesian Optimization*, Distill, 2020 |
| S2 | Frazier, *A Tutorial on Bayesian Optimization*, arXiv:1807.02811, 2018 |
| S3 | Snoek, Larochelle & Adams, *Practical Bayesian Optimization of Machine Learning Algorithms*, NIPS 2012 |
| S4 | Malu, Dasarathy & Spanias, *Bayesian Optimization in High-Dimensional Spaces: A Brief Survey* |
| S5 | Foldager et al., *On the Role of Model Uncertainties in Bayesian Optimization*, PMLR v216 |

PDF 檔請放入 `sources/`（S1 為網頁文章，可存成 PDF）。

## 工作流程概要

```
sources/ → Ingest（讀取、標主張 ID、寫入前自檢）→ wiki/
        → Lint（機械＋語意檢查）→ 規劃簡報（頁 ↔ 主張 ID）→ slides/
```

- 知識單向流動，簡報只能使用 Wiki 內的主張，不得直接使用來源或模型記憶。
- 每則主張都有編號與來源（例如 C3.2 ← S1），簡報每頁底部標示對應編號。
- 來源矛盾或證據不足的內容放在 `wiki/index.md` 的 Open 清單，不進簡報。
- 詳細規則、檢查項目與重試上限見 `AGENTS.md`。

## 目前狀態與已知限制

- Lint 的機械檢查（孤兒頁、連結有效性等）目前為人工判斷，尚未用程式實際執行。
- `AGENTS.md` 是在第一輪建 Wiki 與簡報之後整理而成，尚未用它從頭重跑驗證。
- 簡報中的 Gaussian process 圖為示意圖，非實際資料。

## 如何與 AI 一起維護

1. 把新來源放進 `sources/`。
2. 請 AI 先讀 `AGENTS.md`，再依規範 ingest（一次一篇）並更新 `wiki/`。
3. 請 AI 執行 Lint，把結果寫入 `wiki/index.md`。
4. 需要更新簡報時，先請 AI 列出「頁 ↔ 主張 ID」對照，再產生內容。

## 引用說明

Wiki 內容為對來源的摘要與改寫，不轉錄原文、公式或圖表；直接引文皆少於 15 個字。完整內容請閱讀原始來源。
