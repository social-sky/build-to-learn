---
name: build-to-learn · local-adapters
parent: SKILL.md
applies_to: social-sky/build-to-learn fork only
---

# 階段文件 5 · 本機適配（local-adapters）

> **本文只存在於 `social-sky/build-to-learn` fork**。upstream `Tasihi89/build-to-learn` 沒有這份。哲學核心仍以 SKILL.md 為準，本檔只負責「**實作落地到本地 skills**」的路由表。
>
> 寫作原則同 SKILL.md：給讀者看、簡短、不堆術語、單真源。

## 為什麼

本地已累積 12 個跟 build-to-learn 哲學高度重疊的 skills（`deep-interview`、`compaction-notepad`、`enactive-agent`、`cisa-tutor`、`darwin-skill`、`okinuno-perspective`、`omega-wiki` 等）。每個都用戶資料 / schema / 慣例成熟。

與其在 fork 裡從零重寫，不如讓 build-to-learn 的 references/* **當薄殼呼叫器**——每階段說「做什麼」，實作指向本地 skill。

**衝突解決原則**：upstream 改哲學 → 跟 upstream；upstream 改實作細節 → 留本地覆蓋。

## 適配總表（每個本地 skill 在 build-to-learn 裡的位置）

| 本地 skill | build-to-learn 階段 | 責任 | 替代/增強 | Fallback |
|---|---|---|---|---|
| `deep-interview` | 立項·劇本拷問 | 5 問 Socratic 釐清 | **替代** | 內嵌 5 問列表 |
| `cognitive-agent` | 立項·翻譯桌 | 四象限分類（KK/KU/UK/UU） | **增強** | 簡單能力塊清單 |
| `deep-research-workflow` | 立項·技術形狀 | 形狀可行性調研 | **增強** | AI 直答 |
| `darwin-skill` | 施工·實驗設計 | validation-gated 撞牆 | **增強** | 撞牆/對照式失敗原版 |
| `skill-composition` | 施工·stage 路由 | skill 呼叫語法 | **增強** | 單 skill 模式 |
| `cisa-tutor` | 通關·大考正題 | SM-2 weak-area routing + 雙語 | **增強** | AI 自出題 |
| `memory-sleep-consolidation` | 通關·續學圖問 | 自動 SM-2 分散重複 | **增強** | 人工續學圖問 |
| `enactive-agent` | 通關·反思 | ActionEffectRecord schema | **增強** | 通關批改段落（純文字）|
| `compaction-notepad` | 筆記·單真源 | `.omo/notepad.md` | **替代** | 學習地圖.md |
| `okinuno-perspective` | 筆記·寫作 DNA | 一元化筆記 + 蔥鮪火鍋 | **心智模型** | SKILL 寫作原則 |
| `omega-wiki` | 筆記·能力庫 | 跨專案可行性索引 | **替代** | `_能力庫.md` |

## 階段路由（每階段呼叫哪個 skill）

```
立項 (1-立项.md)
├─ 進站：deep-interview（5 問 Socratic）
├─ 翻譯桌：cognitive-agent（四象限分類）
├─ 技術形狀：deep-research-workflow
└─ 畫階梯：default（build-to-learn 原版）

施工 (2-施工.md)
├─ 部件圖：default（保留 build-to-learn 原版）
├─ 實驗設計：darwin-skill（validation-gated）
├─ skill 呼叫：skill-composition（語法）
└─ 撞牆講透：default

通關 (3-通关.md)
├─ 大考正題：cisa-tutor SM-2（weak-area routing）
├─ 反思落盤：enactive-agent（reflection schema）
├─ 續學圖問：memory-sleep-consolidation（自動 SM-2）
└─ 能力庫登記：omega-wiki（topic namespace）

筆記 (4-笔记.md)
├─ 現在在哪：compaction-notepad（.omo/notepad.md）
├─ 學習記錄：okinuno-perspective（一元化筆記 DNA）
└─ 跨專案能力庫：omega-wiki
```

## 單真源分工（3 個關鍵決策的具體落地）

| 數據類 | 真源位置 | 鏡像/快照 |
|---|---|---|
| **現在在哪、當前階段進展** | `.omo/notepad.md`（compaction-notepad）| 學習地圖.md 頂部區塊 |
| **跨專案能力塊** | OmegaWiki `topics/build-to-learn/` | `_能力庫.md`（自動生成）|
| **單專案學習記錄** | `學習記錄/S?.md` | （無鏡像，純人讀）|
| **反思 schema** | enactive-agent YAML frontmatter | 通關批改段落（純文字）|
| **雙語 glossary** | cisa-tutor `data/cisa-glossary.json` | （依領域換，可置換）|

> 判據：build-to-learn 原生只管「階段流程」；真源全部下沉到本地既有 skill，build-to-learn 只留指針。

## Fallback 路徑（移除 skill 不破壞 build-to-learn）

每個 skill 都有降級方案：

| 移除 skill | 退化行為 |
|---|---|
| `deep-interview` | 退化為 build-to-learn 內嵌的 5 問劇本拷問 |
| `compaction-notepad` | 真源退回 `學習地圖.md`（不再同步 `.omo/notepad.md`）|
| `cisa-tutor` | AI 自出大考題，無 SM-2 weak-area routing |
| `omega-wiki` | 能力庫退回 `{筆記根目錄}/_能力庫.md` |
| `enactive-agent` | 反思落盤改純文字 YAML 段落 |
| `darwin-skill` | 撞牆實驗退回 build-to-learn 原版 5 種實驗設計 |
| `okinuno-perspective` | 寫作原則退回 SKILL.md 寫作原則 8 條 |
| `memory-sleep-consolidation` | 續學圖問改手動觸發（v2.7 自答式）|
| `cognitive-agent` | 翻譯桌改簡單能力塊標記清單 |
| `deep-research-workflow` | 形狀可行性改 AI 直答 |
| `skill-composition` | 改單 skill 直呼模式 |

## 升級策略

- upstream `Tasihi89/build-to-learn` 改 SKILL.md → **幾乎無衝突**（核心規則本檔不動）
- upstream 改 references/* → 用 git diff 檢查：
  - 改的是「**實作細節**」（檔案路徑、CLI 呼叫、JSON 結構）→ **保留本地覆蓋**
  - 改的是「**哲學**」（鐵律、委託人座標系、應答預算）→ **回灌**到本檔

## 三個關鍵決策（執行原則，不容翻案）

1. **單真源 = `.omo/notepad.md`**（compaction-notepad）—— 不為了 build-to-learn 單獨弄一份學習地圖.md 真源
2. **能力庫 = OmegaWiki topic namespace** —— wiki 天然有 backlink / health check，比裸 markdown 清爽
3. **大考題庫 = cisa-tutor SM-2** —— 825 題 + 雙語 glossary 已驗證，比 AI 自出可靠

## 階段 0/1 待辦

- [x] fork + LICENSE + NOTICE + README（已 commit）
- [ ] 寫 5-local-adapters.md（**本檔**）
- [ ] 在 fork 內設 `.omo/notepad.md` 範本
- [ ] 改寫 1-立项.md 的劇本拷問段（指向 deep-interview）
- [ ] 改寫 3-通关.md 的大考段（指向 cisa-tutor SM-2）
- [ ] 改寫 4-笔记.md 的真源分工（指向 compaction-notepad + omega-wiki）
- [ ] 第一次 smoke test（跑一個 2-3 階段的小專案）