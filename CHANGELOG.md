# CHANGELOG — 2026全球AI最強神級天梯榜 ULTIMATE

本檔案記錄歐姆AI天梯榜專案的版本演進歷史（本輪 v9.4.0 → v9.5.2）。
檔案位置：`G:\Ohm\03_專案\14_OhmAIRank_歐姆AI天梯榜\`
開源同步倉庫：https://github.com/junglin830/ohm-ai-tierlist （對外服務走 https://go.yuemoon-osclaw.workers.dev/tierlist）

---

## v9.5.2 — 2026-10-22

**天梯榜表格列也套用去背品牌Logo**

- 新增 `BRAND_LOGOS` 物件 + `findBrandLogo(item)` 比對函式，依 `item.name`/`item.developer` 關鍵字自動配對品牌（claude／openai／ideogram／elevenlabs／gemini／suno／tripo／grok／seedance，共9個品牌）。
- 10個分頁（不只快選榜）的表格第一欄，排名/皇冠圖示之前自動帶出對應品牌去背Logo；沒比對到品牌的項目維持原樣純文字，不受影響。
- 結構驗證：div 122/122、span 87/87、button 17/17 平衡，html.parser 無錯誤。

## v9.5.1 — 2026-10-22

**快選榜獨立成第一個TAB**

- 新增 `quickpick-wrap` / `leaderboard-wrap` 兩個容器，由 `switchTab()` 互斥切換顯示/隱藏。
- 「各領域最佳AI快選榜」改為獨立TAB並放在nav最前面，不再預設全頁常駐顯示，避免畫面預設拉得太長。
- 切到其他10個分頁時快選榜自動隱藏，反之亦然。
- 結構驗證：div 122/122、span 87/87、button 17/17 平衡，html.parser 無錯誤。

## v9.5.0 — 2026-10-22

**新增4大完整天梯分頁**

- 新增「圖片編輯」「生成3D」「語音生成」「個人助手」4個全新完整天梯分頁，共15個新模型項目，每項含 developer／feature／pain／price／baseScore／radar 完整資料結構。
- 「個人助手」分頁收錄2026-10全新發表的真實產品：Claude Duet（Anthropic，10/21發表，Opus 5.5驅動）、Meta Muse、Grok Bot（xAI）、ChatGPT Dots（OpenAI）——因應這些新產品上市，保留此分類而非視為與通用Agent重複。
- 沿用既有 `leaderboardData` / `switchTab` 引擎架構，無需更動底層排序/權重/雷達圖邏輯層。
- nav新增4顆分頁按鈕（含對應 Font Awesome 圖示）。
- 結構驗證：div 120/120、span 87/87、button 16/16 平衡，JS brace 108/108，html.parser 無錯誤。

## v9.4.2 — 2026-10-22

**13格快選榜Logo去背**

- 自行撰寫 `flood_fill_transparent()`：用PIL從圖片四角偵測接近白色的底色，向內flood-fill把符合的背景像素alpha設為0，完成真正去背（非白色方塊貼色）。
- 9個品牌（claude／openai／ideogram／seedance即梦／elevenlabs／gemini／suno／tripo／grok）Logo全部去背成功（9/9）。
- 去背後的PNG轉base64直接內嵌進HTML，不再依賴外部favicon連線，離線也能正常顯示。
- 去背快取圖另存於 `.logo_cache/` 供下次重用。
- 結構驗證：div 120/120、span 87/87 平衡，html.parser 無錯誤。

## v9.4.1 — 2026-10-22

**快選榜13格改用實際品牌Logo**

- 13格中12格換成實際品牌favicon（透過Google favicon服務抓取：claude.ai／openai.com／ideogram.ai／elevenlabs.io／gemini.google.com／suno.com／tripo3d.ai／grok.com等）。
- 附 `onerror` JS備援：圖片載入失敗時自動退回品牌色字首badge，不會開天窗。
- PPT Master Skill（非品牌項目）維持原文字badge設計。
- 已寫入v9.4.1並同步覆蓋 `ai_tierlist.html` 別名檔。
- 結構驗證：div 120/120、span 99/99 平衡，html.parser 無錯誤。

## v9.4.0 — 2026-10-22

**新增「各領域最佳AI快選榜」**

- 仿抖音「各個領域最佳AI」靈感卡片風格（靈感來源：`line_2026-10-22_044626`），新增13類任務對應首選工具的快選榜區塊。
- 每格含編號色塊（01-13）+ 品牌色 + 任務名稱 + 推薦工具 + 簡短說明。
- 參考圖13分類與我方原有6分類比對後，決定新增4個獨立完整分頁（詳見v9.5.0），同時保留快選榜作為快速導覽入口。
- 已寫入v9.4.0並同步覆蓋 `ai_tierlist.html` 別名檔。
- 結構驗證：div 120/120 平衡，html.parser 無錯誤。

---

## 版本對照總覽

| 版本 | 日期 | 核心變更 |
|---|---|---|
| v9.4.0 | 2026-10-22 | 新增13類快選榜區塊 |
| v9.4.1 | 2026-10-22 | 快選榜改用實際品牌Logo（白底） |
| v9.4.2 | 2026-10-22 | 品牌Logo去背（真透明，非白底） |
| v9.5.0 | 2026-10-22 | 新增4大完整分頁（圖片編輯/3D/語音/個人助手），分頁數6→10 |
| v9.5.1 | 2026-10-22 | 快選榜獨立成第一個TAB，不再常駐佔版面 |
| v9.5.2 | 2026-10-22 | 10大分頁表格列全面套用去背品牌Logo |

## 分類架構（v9.5.2 現狀，共10個完整天梯分頁 + 1個快選導覽TAB）

1. 快選榜（各領域最佳AI，13類導覽，非排名分頁）
2. LLM 核心天梯（coding/reasoning）
3. 圖片生成
4. 圖片編輯 🆕
5. 影片生成
6. 生成3D 🆕
7. 音樂生成
8. 語音生成 🆕
9. 通用型AI Agent（OpenClaw風格）
10. 個人助手Agent 🆕（Claude Duet / Meta Muse / Grok Bot / ChatGPT Dots）
11. AI coding-agent 軟體（IDE/CLI工具）

🆕 = 本輪新增分類
