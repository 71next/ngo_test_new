# Skill 清單與用途

> 更新日期：2026-10-05（清理與修正之後）
>
> 呼叫方式：
> - **自動**：符合描述時，Claude 會自己載入。
> - **手動**：只能自己打 `/名稱` 呼叫。
>
> 在 Claude Code 裡，任何 skill 都可以打 `/名稱` 呼叫。

## 1. 自己安裝的（`~/.claude/skills/`）

| Skill | 用途 | 呼叫方式 | 來源 |
|---|---|---|---|
| `codebase-memory` | 用程式碼知識圖譜查結構、呼叫鏈、影響範圍、死碼 | 自動 | codebase-memory MCP |
| `find-skills` | 搜尋、安裝新 skill | 自動 | 第三方 |
| `git-commit-helper` | 分析變更，產生中文 Conventional Commits 並執行 commit | 自動 | 自己寫的 |
| `goldfish` | 查這台電腦上的過去活動、人物、專案、時間統計 | 自動 | Goldfish App |
| `grilling` | 連續追問，壓力測試計畫或決策 | 自動 | 第三方 |
| `grill-me` | 啟動一次 `/grilling` 追問 | 手動 | 第三方 |
| `handoff` | 把目前對話濃縮成交接文件，給下一個 agent 接手 | 手動 | 第三方 |
| `maintain-log` | 把修改或問題盤查寫入 `future/maintain.md`、`future/分析功能.md` 與 `docs/` | 自動 | 自己寫的 |
| `organize-desktop` | 整理桌面、下載或指定資料夾，依檔案類型分類，截圖移到垃圾桶 | 自動 | 自己寫的 |
| `project-handover-guide` | 為接手專案的人產生交接文件（快速開始、結構、git 熱點、維護注意） | 自動 | 自己寫的 |
| `sdd-claude-code` | 規格驅動開發：需求 → spec.md → plan.md → tasks.md → 實作 | 自動 | 自己寫的 |
| `teach` | 跨多次對話、有學習紀錄的教學 | 手動 | 第三方 |
| `web-slides` | 製作單一 HTML 檔的 16:9 網頁簡報，開工前先問風格 | 自動 | 自己寫的 |
| `writing-great-skills` | 撰寫和修改 skill 的原則參考 | 手動 | 第三方 |

## 2. claude.ai 同步的 skill（前綴 `anthropic-skills:`）

在 claude.ai 的設定 → 功能 → Skills 管理，單向同步到本機 `~/.claude/skills/synced/`。

| Skill | 用途 |
|---|---|
| `contract-selector` | 依情境挑選合約或收據範本，填入甲方資訊、金額、範圍（自己上傳的） |
| `doc-coauthoring` | 用結構化流程共同撰寫文件、提案、規格 |
| `docs` | 建立可分享、可留言的 Claude Docs 文件 |
| `docx` | 讀寫、編輯 Word 文件 |
| `pdf` | 讀取、合併、分割、填表、OCR 等 PDF 處理 |
| `pptx` | 讀寫、編輯 PowerPoint 簡報 |
| `xlsx` | 讀寫、整理 Excel 和 CSV 試算表 |
| `google-workspace` | 建立或修改 Google 文件、試算表、簡報 |
| `import-memory` | 匯入其他 AI 助理的記憶 |
| `mcp-builder` | 開發 MCP server 的指南 |
| `morning` | 產生晨間簡報，或設定成每個工作日自動產生 |
| `skill-creator` | 建立、修改 skill 並評估成效 |
| `third-force-transformation` | 面對二選一困境時，找出兼顧兩邊的第三種解法 |

## 3. Plugin 帶來的 skill

### engineering（claude.ai 同步）
| Skill | 用途 |
|---|---|
| `architecture` | 建立或評估架構決策紀錄（ADR） |
| `code-review` | 審查程式碼的安全性、效能、正確性 |
| `debug` | 結構化除錯：重現 → 隔離 → 診斷 → 修復 |
| `deploy-checklist` | 部署前檢查清單 |
| `documentation` | 撰寫技術文件、README、runbook |
| `incident-response` | 事故處理流程與事後檢討 |
| `standup` | 從近期活動產生站會報告 |
| `system-design` | 系統、API、資料模型設計 |
| `tech-debt` | 盤點技術債並排出優先順序 |
| `testing-strategy` | 設計測試策略和測試計畫 |

### figma（claude.ai 同步）
Figma 設計轉程式碼、程式碼轉設計、Code Connect、設計系統、FigJam 圖表、Slides、動畫、Shader、SwiftUI 等，共約 14 個。

### cowork-plugin-management（claude.ai 同步）
| Skill | 用途 |
|---|---|
| `cowork-plugin-customizer` | 依組織需求客製化 plugin |
| `create-cowork-plugin` | 從零建立新 plugin |

### codex（OpenAI，自己安裝）
| Skill | 用途 |
|---|---|
| `rescue` | 卡住時把調查或修復交給 Codex |
| `setup` | 檢查 Codex CLI 狀態，切換審查設定 |

另外有 3 個內部輔助用的 skill：`codex-cli-runtime`、`codex-result-handling`、`gpt-5-4-prompting`。

## 4. Claude Code 內建的 skill

| Skill | 用途 |
|---|---|
| `code-review` | 審查目前的改動或 PR，找出 bug |
| `simplify` | 精簡改動過的程式碼（不找 bug） |
| `security-review` | 審查目前分支的安全性 |
| `init` | 產生專案的 CLAUDE.md |
| `loop` | 定時重複執行某個指令 |
| `schedule` | 建立雲端排程 agent |
| `run` | 啟動並操作專案的 App 來驗證改動 |
| `update-config` | 修改 settings.json（權限、hooks、環境變數） |
| `keybindings-help` | 自訂快捷鍵 |
| `fewer-permission-prompts` | 掃描紀錄，自動加入常用指令的允許清單 |
| `claude-api` | Claude API 和 Anthropic SDK 的參考 |
| `claude-in-chrome` | 操作 Chrome 瀏覽器 |
| `plugin-authoring` | 撰寫 Claude Code 外掛 hooks |
| `dataviz` | 製作圖表與資料視覺化的設計規範 |
| `artifact-design` / `artifact-diagramming` / `artifact-capabilities` | 製作 Artifact 網頁的設計、圖表和執行期功能 |
| `mode` | 切換互動模式 |
