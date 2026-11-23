# Apex 身法 LLM Wiki

用 LLM Wiki 做一份教學 HTML 簡報：主題是 Apex Legends 的身法技巧（兔子跳、Tap Strafe、蹬牆跳、超級滑翔、滑索技巧）。

- **網頁**：https://0chanchuan0.github.io/apex-movement-wiki/
- **教學簡報**：https://0chanchuan0.github.io/apex-movement-wiki/slides/
- **Wiki 目錄**：[index.md](index.md)
- **規則檔（schema）**：[CLAUDE.md](CLAUDE.md)
- **流程與檢查紀錄**：[process/](process/)

## 結構

```
CLAUDE.md   Wiki 規則：目錄、頁面格式、分級、ingest / query / lint 流程
index.md    Wiki 目錄
log.md      操作日誌
raw/        8 篇原始資料（S01–S08，含網址、日期、版本、疑點）
wiki/       9 個 Wiki 頁面（每句標註 [Sxx] 來源）
slides/     教學 HTML 簡報（只使用 Wiki 的內容）
process/    討論紀錄、loop/graph 設計、檢查報告、反思
```

使用模型：Claude Opus 5.5（主流程，Claude Code）＋ Claude Sonnet（子代理：收集資料、Lint、簡報檢查）。
