# 操作日誌（log）

> 每次 ingest / query / lint / 生成都追加一筆，格式：`## [日期] 操作 | 說明`

## [2026-11-23] discuss | 確定主題與範圍
- 主題：Apex 身法教學。分級討論後 Tap Strafe 改列中階。
- 使用者要求 5 篇資料排除滑鏟、攀爬、跳躍等基本操作 → 修改分級，並當場通知收資料的子代理改方向。
- 詳見 `process/01-討論紀錄.md`。

## [2026-11-23] schema | 建立 CLAUDE.md
- 定義目錄、頁面格式、分級規則、ingest / query / lint 流程。

## [2026-11-23] fetch | 派 3 個 Sonnet 子代理並行收集 S01–S06
- A：社群 Wiki + 官方 patch 歷史；B：入門/中階技巧；C：進階技巧與輸入裝置差異。

## [2026-11-23] ingest | S01、S02（子代理 A）
- 時效檢查發現：討論時 AI 憑記憶說「Tap Strafe 2021 年被削弱又撤回」，S02 只能確認「宣布移除 → 延後」，撤回日期不明 → 討論紀錄加註，待補資料。

## [2026-11-23] ingest | S03、S04（子代理 B）、S05、S06（子代理 C）
- S03 vs S04 步驟衝突（撥滾輪 vs 連點 Space）→ 記錄，待裁定。
- **缺口**：Lurch 定義、Bunny Hop 時機沒有可讀來源；Mantle Jump、Neo Strafe 沒有來源 → 後兩者移出範圍。

## [2026-11-23] fetch（回流）| 補資料 S07、S08
- S07 找到 2025-01 Season 23「加緩衝 → 撤回」的日期，解決「撤回」時間問題。
- Lurch 定義仍是缺口 → 標記，不由模型補。

## [2026-11-23] write | wiki/ 9 頁 + index.md

## [2026-11-23] lint 第 1 輪 | 獨立 Sonnet → process/lint-report-round1.md
- 37 項（高 3／中 14／低 20）。高：全部是「把 S03 的斜向拉力等同於 Lurch」並掛上來源標記。
- 修正：lurch.md 拆出「推論」段；bunny-hop.md 區分滑鏟跳與兔子跳、補治療衝突；frontmatter 對齊；version-history 可信度下修、補未查範圍與 27.0.2。
- **規則修改**：CLAUDE.md 進階判斷標準補 2 項；Ingest 加「引用自我檢查」（把 lint 的檢查往前移）。

## [2026-11-23] query → generate | slides/index.html（18 頁）
- 依 lint 修正同步改簡報：Lurch 不下定義、兔子跳步驟、手把表、測驗答案。
- 瀏覽器實測：修正原理圖、手機版來源列重疊、表格換行。

## [2026-11-23] check | 簡報檢查第 1 輪（獨立 Sonnet）→ process/slide-check-round1.md
