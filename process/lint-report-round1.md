# Lint 報告 第 1 輪

範圍：`wiki/` 9 頁 + `index.md`，對照 `raw/` S01–S08（僅以 raw 為依據，未上網、未改任何檔案）。

## 全域檢查結果
- [[links]]：所有連結目標都存在，無斷鏈。
- 孤立頁面：9 頁皆被 `index.md` 連到，無孤立頁。
- 分級規則（基本操作不得自成內容）：無違規。`zipline-tech.md` 已明說不收「上滑索」。

## 問題清單

| 頁面 | 位置/句子 | 問題類型 | 說明 | 嚴重度 |
|---|---|---|---|---|
| lurch.md | 「Lurch 是 tap-strafe 裡『方向被拉過去』…的名稱 [S04][S07]」 | 引用不支持 | S04 只在更新紀錄出現 lurch 一詞，明說「沒有給定義」；S07 也寫「仍缺 lurch 的定義」。「方向被拉過去」是 S03 對 tap strafe 的描述，不是 lurch 的定義。此句與同頁「缺口」段自相矛盾。 | 高 |
| lurch.md | 「它的效果就是 S03 描述的原理…[S03]」 | 引用不支持／錯誤來源 | S03 全文沒有提到 lurch。S03 疑點段明說不能把它與 lurch 事件直接等同。把 lurch 等同於 S03 原理是模型推論。 | 高 |
| tap-strafe.md | 「…稱為 **Lurch** [S04][S07]，見 [[lurch]]」 | 引用不支持 | 與 lurch.md 同一問題：S04、S07 都沒有 lurch 的定義，只有名詞出現。這句使缺口被當成已知事實。 | 高 |
| lurch.md | 「替 Lurch 和換方向之間加了延遲 [S07]」 | 來源範圍 | S07 說 lurch 與巨集兩詞僅見於 PCGamesN，GameRant 沒提。引用本身可用，建議註明只有單一來源。 | 低 |
| bunny-hop.md | frontmatter `sources` | frontmatter 不一致 | 內文引用 [S03]（「為什麼是入門」），但 sources 沒有 S03。 | 中 |
| bunny-hop.md | 步驟 1–2「滑鏟快結束時按跳躍 [S06][S08]」 | 引用不支持／混淆 | 這是 Charlie Intel 的 slide jump。S06 摘要明說「沒有談兔跳」，S08 也把 slide jump 與 bunny hop 分開。S01 對 bunny hop 的定義是「快速小跳、少接地」，沒有滑鏟。頁面把兩種技巧混成一個，並用 S06 支持 bunny hop。 | 中 |
| bunny-hop.md | 步驟 3「落地後立刻接下一次」vs 常見錯誤「兩次之間要留時間」 | 內部矛盾／來源衝突 | 步驟 3 引 S01（縮短接地），常見錯誤引 S06/S08（slide jump 要留足時間）。兩者建議相反，頁面沒有標成衝突，也沒說明前者指 bunny hop、後者指 slide jump。 | 中 |
| bunny-hop.md | 「限制：使用回復道具…無法兔子跳 [S01][S08]」 | 忽略 raw 衝突 | S08 的 MeinMMO 說 bunny hop 用途之一是「邊移動邊治療」，Charlie Intel 說可在滑行前先治療。這與 wiki.gg 的限制衝突，「來源衝突」段沒有記錄。 | 中 |
| bunny-hop.md | 「是漏洞修正，不影響一般兔子跳」 | 無標註的推論 | S02 只寫修正 Death Box 重生互動期間的 bunny hop 漏洞，沒有說不影響一般兔子跳。 | 低 |
| bunny-hop.md | 「沒有單幀時機」；「也是 tap-strafe、wall-bounce 的起手動作 [S03][S06]」 | 無標註／來源偏弱 | S08 疑點說缺少精確節奏數據，不能斷言沒有單幀時機（屬分級理由，可接受）。S06 的蹬牆跳起手是 slide jump，不是 bunny hop。 | 低 |
| bunny-hop.md | `version_status: current` | 版本標示 | 來源是 2019/2021 年文章，S08 自己提醒細節可能過時，version-history 也沒有涵蓋 bunny hop。與 wall-bounce、zipline 的 `unknown` 標準不一致，建議改 `unknown`。 | 低 |
| kbm-vs-controller.md | frontmatter `sources` | frontmatter 不一致 | 表格引用 [S03]，另在文字提到「S03、S04」，sources 都沒有 S03、S04（S04 的提及沒有加 [Sxx] 標記）。 | 中 |
| kbm-vs-controller.md | 表格「bunny-hop｜手把：可以」[S06][S08] | 引用不支持／忽略衝突 | S06、S08 談的是 slide jump 的手把按鍵配置，沒有直接說手把能做 bunny hop。S06 疑點記載有搜尋摘要稱「手把不能兔跳」（未採信），本頁的「來源衝突」只寫了蹬牆跳，沒寫兔跳。 | 中 |
| kbm-vs-controller.md | 「只有社群 Wiki 一方說法 [S01][S08]」 | 說法不精確 | S01 與 S08 的 wiki.gg 部分都屬社群 wiki，並非兩個獨立來源。S04 備註另有 DBLTAP（2021）也稱手把做不到（未計入 urls）。「一方說法」大致成立，但應註明 S04 備註這一條。 | 低 |
| overview.md | frontmatter `sources` | frontmatter 不一致 | 「時效提醒」引用 [S07]，sources 沒有 S07。 | 中 |
| overview.md | 「Tap Strafe 在 2021、2025 兩次被調整 [S02][S07]」 | 引用過度 | S02 對 2021 只確認「宣布移除 → 延後」，且明說無法證實 2021 年有反轉。「被調整」的依據是 S03（未標）。version-history 已特別糾正這種講法，此處措辭容易讓人誤解。 | 中 |
| overview.md | 「更難被打中：空中急轉…[S03]」 | 引用不支持 | S03 只說轉彎更銳利，沒有提到閃避或難被打中。「用來閃避火力」在 S07（PCGamesN）。 | 低 |
| overview.md | 分級表「進階：需要精準時機（碰牆瞬間、單幀）」 | 分級理由 vs 來源 | S06 明說蹬牆跳沒有影格級時機，zipline-tech 也無此依據。進階分級本身符合 CLAUDE.md（蹬牆跳、超級滑翔），但理由句對蹬牆跳、滑索不精確。 | 低 |
| super-glide.md | 步驟 4「鍵盤方向鍵或手把左搖桿 [S05]」 | 細節超出來源 | S05 只寫「方向鍵／搖桿」，沒有指明鍵盤 WASD 或左搖桿。 | 低 |
| super-glide.md | 「S01 寫『最高點』，S05 寫『即將結束時』，可視為同一時刻」 | 無標註的推論 | 這是模型的調和，沒有來源支持。應改寫成「兩者措辭不同，是否同一時刻未確認」。 | 低 |
| super-glide.md | 「手把同樣是同時按下跳躍與蹲下 [S05]」 | 忽略 raw 衝突 | S05 疑點提到其他站稱「接近同時、略有先後」，與 Setup.gg「同時按下」可能不一致。頁面未記錄。 | 低 |
| tap-strafe.md | 「鍵鼠改一個滾輪綁定就能開始練，不需要…抓單幀時機」 | 無標註 | 屬分級理由（使用者決定）。但 S03、S04 都強調滑跳時機要順，S03 沒給綁定設定細節，S07 還暗示高 FPS 影響。建議標註這是使用者判斷，而非來源事實。 | 低 |
| tap-strafe.md | 「目前（2026-11）視為仍可使用」 | 無標註 | 依據只有 S04（2025-09）與 S02（只讀兩份 patch notes），沒有標來源，也沒寫 Season 30 未查（version-history 有寫）。 | 低 |
| tap-strafe.md | 步驟 3「其他三個來源都是…[S01][S03][S08]」 | 計數不精確 | S01 與 S08 的相關內容都來自 wiki.gg，並非兩個獨立來源。 | 低 |
| version-history.md | frontmatter `sources` | frontmatter 不一致 | 列了 S01，但內文沒有任何 [S01] 標記（多餘）。 | 中 |
| version-history.md | 2026-05-04 列「高（官方）」 | 可信度過度 | S02 說這些 patch notes 是 WebFetch 小模型摘要，非逐字，只讀兩份。S02 說「未見改動」不代表不存在。「沒有改到 Super Glide/Tap Strafe」不該評為高，建議中。 | 中 |
| version-history.md | 「未查過的範圍：Season 30 與其他中期更新」 | 漏記時效風險 | S05 提到 Season 27 的 27.0.2 熱修可能影響超級滑翔（未讀原文），S02 另有 2026-06-22 中期更新（只有二手摘要）。時間線與未查範圍都沒提 Season 24–28、27.0.2。Super Glide 的「大致仍可用」因此偏樂觀。 | 中 |
| version-history.md | 「目前狀態」整段 | 無標註 | 事實性陳述（兩份 patch notes、2025-09 教學）沒有 [Sxx]。 | 低 |
| version-history.md | 時間線 | 與子頁不一致 | zipline-tech 引用 S02 的 Broken Moon 滑索移除、Season 31 選錯滑索修正，但「時效基準」頁沒有這些事件，zipline-tech 仍標 `unknown`。 | 低 |
| wall-bounce.md | frontmatter `sources` | frontmatter 不一致 | 內文引用 [S02]（時效註記），sources 只有 S01、S06。 | 中 |
| wall-bounce.md | 「2026 年官方 patch notes 未提到相關改動 [S02]」 | 引用過度 | S02 的「未提及」清單只列衝刺、翻越、超級滑翔、tap strafe，沒有蹬牆跳。S31 還有「多處黏牆碰撞」修正，可能相關，頁面沒提。 | 中 |
| wall-bounce.md | 「沒有容錯的時間窗；來源都沒有給出影格級的時機數字 [S06]」 | 引用過度／自相矛盾 | S06 只說「正好碰牆時」是口語描述，沒有說沒有容錯。「沒有容錯」是推論。後半句又承認無數字。 | 中 |
| wall-bounce.md | 「甩開敵人」 | 引用不支持 | S01、S06 沒有這個用途。S01 寫「越過障礙」，S06 寫滑索上成為難打的目標。 | 低 |
| wall-bounce.md | 整頁引用 S01 | 來源可信度 | S01 自己說 Wall Bounce 描述經摘要模型轉述，建議自行核對，頁面沒提。 | 低 |
| wall-bounce.md | 「為什麼是進階」 | 分級理由 | 依 CLAUDE.md 蹬牆跳列為進階沒問題。但頁面自己證明沒有單幀時機，與「單幀/特定 FPS 才算進階」的判斷標準不符，建議在頁面說明進階是依規則表指定。 | 低 |
| zipline-tech.md | 分級 `進階` | 分級理由缺失 | CLAUDE.md 沒有列出滑索技巧的分級，頁面也沒有「為什麼是進階」的說明。S06 沒有給出難度或時機資訊。 | 低 |
| index.md | 「頁面 10 頁」 | 計數錯誤 | `wiki/` 實際 9 頁（總覽 + 6 技巧 + 鍵鼠 vs 手把 + 改版時間線）。 | 低 |

## 乾淨項目
- zipline-tech.md：所有 [S06]/[S02] 引用皆與 raw 相符，frontmatter 正確（僅分級理由缺失一項）。
- super-glide.md：frontmatter 與引用相符，10.3 m/s、FPS 單一來源、27.0.2 不採用皆處理得當（僅上列 3 個低度問題）。
- 斷鏈、孤立頁、基本操作越界：無。

## 統計
- 高：3
- 中：14
- 低：20
- 合計：37
