# Apex 身法教學 LLM Wiki — 規則檔（Schema）

本專案是一個 **LLM Wiki**：由 LLM 讀取原始資料（raw），整理、交叉檢查後寫成互相連結的 Wiki 頁面，再以 Wiki 為唯一知識來源產生教學簡報。

## 目錄結構

```
apex-movement-wiki/
├── CLAUDE.md          ← 本規則檔（LLM 每次操作前必讀）
├── index.md           ← Wiki 目錄：每頁一行，含難度與一句話摘要
├── log.md             ← 操作日誌：每次 ingest / query / lint / 生成都追加一筆
├── raw/               ← 原始資料（只讀，ingest 後不再修改）S01、S02…
├── wiki/              ← Wiki 頁面（LLM 維護）
├── slides/index.html  ← 教學 HTML 簡報（由 Wiki 產生）
└── process/           ← 討論紀錄、loop/graph 設計、檢查紀錄、反思
```

## 三種操作

### 1. Ingest（加入資料）
1. 新資料存成 `raw/SXX-slug.md`，frontmatter 必須有 `urls`、`retrieved`、`version_context`。
2. **時效檢查（ingest 當下就做）**：資料的發布日期 / 對應賽季是否早於最近一次相關改版？是的話在 raw 檔的「版本／時效註記」標記，並查 `wiki/version-history.md` 確認現況。
3. 把新資料的事實寫進對應的 Wiki 頁面（沒有就新建），每個事實後面標來源 `[S03]`。
4. 和既有內容衝突時，**不覆蓋**：寫進該頁的「來源衝突」段落，註明各來源說法。
5. **引用自我檢查（lint 第 1 輪後新增，從 Lint 往前移到 Ingest）**：每寫完一頁，逐句確認——
   - `[SXX]` 標的內容真的出現在 raw/SXX 裡，不是「看起來合理」的延伸；
   - 把兩個來源的說法「調和」、或把某現象「等同於」某術語，屬於**推論**，要放進「推論」段落，不能掛來源標記；
   - frontmatter `sources` 和內文引用一致；
   - raw 檔「可信度與疑點」裡的衝突都有搬到頁面的「來源衝突」段。
6. 更新 `index.md` 與 `log.md`。

### 2. Query（查詢 / 生成）
- 回答問題或生成簡報時，**只能使用 Wiki 頁面的內容**，不可以直接用模型自己的記憶補資料。
- Wiki 沒有的內容 → 標記為「缺口」，回到 Ingest 補資料，而不是自己編。
- 簡報每一張技巧投影片都要能對應到某個 Wiki 頁面（在 speaker notes / 註解中寫 `wiki: xxx.md`）。

### 3. Lint（健康檢查）
- 每個事實都有 `[SXX]` 來源標記？
- 頁面 frontmatter 的 `version_status` 是否和 `version-history.md` 一致？
- 有沒有孤立頁面（沒有被任何頁面或 index 連到）？
- 難度分級是否符合下方「分級規則」？

## Wiki 頁面格式

```markdown
---
title: 中文名稱（English Name）
tier: 入門 | 中階 | 進階 | 概念
sources: [S01, S03]
version_status: current | changed | unknown   # 是否受改版影響
last_checked: YYYY-MM-DD
---
# 標題
## 一句話說明
## 怎麼做（步驟）
## 常見錯誤
## 鍵鼠 vs 手把
## 來源衝突 / 時效註記
## 相關頁面
```

## 分級規則（討論後決定，見 process/01-討論紀錄.md）

| 分級 | 內容 |
|---|---|
| 前置（不收錄） | 衝刺、滑鏟、跳躍、攀爬、滑索等**遊戲基本操作**：不 ingest、不建頁，簡報只用一行帶過「假設你已會」 |
| 入門 | 兔子跳（Bunny Hop）等「把基本操作串起來保留速度」的技巧 |
| 中階 | **Tap Strafe**、Lurch（原理） |
| 進階 | 蹬牆跳（Wall Bounce）、超級滑翔（Super Glide）、攀爬跳（Mantle Jump）等 |

- 基本操作不算身法技巧，**不列入 5 篇 ingest 資料的主題**（使用者決定）。
- Tap Strafe 依使用者意見列為**中階**：原理（Lurch）好理解，鍵鼠只要改綁滾輪就能練，不需要逐幀時機。
- 判斷標準（lint 第 1 輪後修訂）：符合任一項 → 進階
  1. 需要單幀（frame-perfect）輸入窗口（例：Super Glide）
  2. 需要在某個特定瞬間輸入（例：Wall Bounce 的碰牆瞬間）
  3. 要先會另一個進階技巧才能組合（例：垂直滑索接蹬牆跳）
- 原本只寫第 1 項，lint 發現 Wall Bounce、滑索技巧都不符合卻被列為進階，規則和頁面矛盾，所以補上 2、3 項。
- 分級理由如果是使用者或規則的判斷、不是來源事實，頁面上要寫清楚「依分級規則」或「使用者判斷」。

## 寫作規則
- 繁體中文；遊戲術語第一次出現時附英文，例如 超級滑翔（Super Glide）。
- 用自己的話改寫來源，不整段複製；引用原文不超過 15 字。
- 不確定的事寫「未確認」，不要猜。
