# Active Context Notepad — build-to-learn project

> 這份是 `build-to-learn` 學習專案的「現在在哪」真源。每次 session 第一件事讀它。
> 由 `compaction-notepad` skill 管理；由 AI 在每個關鍵節點自動刷新。
> **佔位符說明**：`{專案名}` / `{ISO 8601}` / `{階段}` 用真值替換。

## Current Goal
{一句話：我們在做什麼 + 我們要學什麼}

## Key Decisions Made
- [{YYYY-MM-DD}] {決策}: {理由}

## Active Constraints
- {約束條件 e.g. 必須用 Python 3.12+}

## Progress
- [x] S1 ✅ {標題}（{YYYY-MM-DD} 通關）
- [ ] S2 🔄 {標題}（{YYYY-MM-DD} 開工）
- [ ] S3 ⬜ {標題}

## Stage Component Diagram (current)
{Mermaid 部件圖——從 `學習記錄/S?.md` 頂部施工態區同步過來}

## ⏸ Hand-off Position (most important)

**手正懸在哪一步**：
{具體到部件 + 邊，例如：A → B 邊講完，B 機制講清，B 代碼已寫但未跑}

**AI 上一步做完什麼**：
{一句話}
- 搭台：起好什麼環境
- 寫：改了哪些檔
- 講：講了什麼邏輯（不含代碼）
- 交棒：要 user 做什麼}

**下一步動作（user）**：
{具體到那一條命令 / 那一個按鈕}

## Code State Snapshot

| 檔案 | 狀態 | 備註 |
|---|---|---|
| `path/to/file.py` | ✅ 寫好 / 🔄 半成品 / ⬜ 未動 | {一句話說明它做什麼、目前長什麼樣} |
| | | |
| | | |

## How to Restart Environment

```bash
cd ~/Projects/{專案名}
{啟動服務的命令}
```

- 改了 X 要重啟；改了 Y 熱更新

## Files Modified This Session
- `path/to/file`：{改了什麼、為什麼}

## Pending Verification
- [ ] {跑通測試 1}
- [ ] {跑通測試 2}

## Important Context

{任何昂貴重發現的 context——API contracts, data formats, env quirks}

---

> **真源位置**：`./.omo/notepad.md`（項目根目錄）。
> **鏡像位置**：`學習地圖.md` 頂部（給人看的快照，AI 不直接讀）。
> **更新觸發**：每改代碼、每交棒給 user、user 說「存檔/刷新/先到這」、session 結束前。
> **跨 session 接管**：新對話第一件事讀這份；按 SKILL 開場協議接上。

> 範本由 [`social-sky/build-to-learn`](https://github.com/social-sky/build-to-learn) 維護。詳見 [`references/5-local-adapters.md`](https://github.com/social-sky/build-to-learn/blob/main/references/5-local-adapters.md) §單真源分工。