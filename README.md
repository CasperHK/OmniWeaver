# 🌐 OmniWeaver

[![Wails](https://shields.io)](https://wails.io)
[![Svelte](https://shields.io)](https://svelte.dev)
[![Go](https://shields.io)](https://go.dev)
[![License](https://shields.io)](LICENSE)

> **OmniWeaver** 是一款專為現代開發者打造的**智慧型跨平台多資料庫用戶端**。承襲了經典資料庫工具的多相容性，並融入強大的 AI 驅動核心，透過輕量、極速的架構，將複雜的資料庫網絡完美交織在一起。

有別於傳統基於 Electron、記憶體消耗龐大的 GUI 工具，OmniWeaver 採用 **Wails (Go)** 作為後端配合 **Svelte** 輕量前端，帶來秒開、低內存佔用且如絲般順滑的原生桌面應用體驗。

---

## ✨ 核心特性

- 🔗 **萬能連線 (Omni-Connectivity)**：單一工具即可同時管理多種不同的資料庫，支援 PostgreSQL、MySQL、SQLite、SQL Server、Redis 等。
- 🧠 **AI 智慧編織 (AI-Driven Context)**：
  - **Text-to-SQL**：使用自然語言直接向 AI 提問（例如：「幫我找出上個月消費最高的前十名用戶」），自動生成精準的 SQL 語句。
  - **結構感知 (Schema-Aware)**：AI 會自動讀取當前資料表的 DDL 結構作為上下文，拒絕瞎猜，生成 100% 符合業務的查詢。
  - **SQL 自動修正 (SQL Auto-Fix)**：當執行 SQL 發生錯誤時，AI 能即時捕獲錯誤訊息並自動提供修正建議。
- ⚡ **極致效能 (Svelte + Wails)**：
  - 放棄虛擬 DOM，採用 Svelte 原生響應式 UI，介面操作毫無延遲。
  - 後端由 Go 語言驅動，直接調用底層資料庫 Driver，極速處理海量數據。
- 🎨 **現代化 UI/UX**：簡潔、現代化的深色/淺色模式介面，內建智慧 SQL 編輯器與動態數據視覺化建議。

---

## 🛠️ 技術棧

- **後端 (Backend)**: Go 1.22+ / Wails v2 或 v3
- **前端 (Frontend)**: Svelte / Vite / Tailwind CSS
- **AI 整合 (AI Integration)**: 支持本地 Ollama (如 DeepSeek-R1 / Llama3) 及 雲端 OpenAI API
- **數據庫驅動**: Go 原生 `database/sql` 生態系與 GORM

---

## 🚀 快速開始

### 前置需求

在開始之前，請確保你的開發環境已安裝以下工具：
- [Go](https://go.devdoc/install) (v1.22 或更高版本)
- [Node.js](https://nodejs.org) 與 npm/pnpm/bun
- [Wails CLI](https://wails.iodocs/gettingstarted/installation)

### 安裝與運行

1. **複製專案庫**
   ```bash
   git clone https://github.com
   cd OmniWeaver
   ```

2. **以開發模式啟動應用程式**
   運行以下指令，Wails 將會自動編譯 Go 後端、安裝前端依賴並啟動帶有熱重載 (Hot-Reload) 的桌面視窗：
   ```bash
   wails dev
   ```

3. **編譯正式發行版 (Production Build)**
   編譯出體積超小、效能優化的原生二進位檔案 (.exe, .app, 或 Linux 執行檔)：
   ```bash
   wails build
   ```
   編譯完成後的安裝包將會輸出至 `build/bin/` 目錄。

---

## 📂 專案目錄結構

```text
OmniWeaver/
├── app.go              # Go 後端核心邏輯 (資料庫連線、AI 橋接與 Binding)
├── main.go             # 應用程式入口與 Wails 初始化配置
├── wails.json          # Wails 專案配置文件
├── frontend/           # Svelte 前端專案
│   ├── src/
│   │   ├── App.svelte  # 前端主要 UI 介面
│   │   └── main.js
│   ├── tailwind.config.js
│   └── vite.config.js
└── build/              # 圖標及編譯輸出的二進位檔案
```

---

## 💡 AI 功能配置說明

OmniWeaver 預設支援兩種 AI 模式：
1. **本地隱私模式 (推薦)**：安裝並啟動 [Ollama](https://ollama.com)，在設定中將 API Endpoint 指向 `http://localhost:11434`，即可完全在本地進行 Text-to-SQL，保障企業資料隱私。
2. **雲端高效模式**：在設定介面填入你的 OpenAI 或其他 LLM 供應商的 API Key 即可直接啟用。

---

## 🤝 貢獻指南

我們非常歡迎任何形式的貢獻！無論是回報 Bug、提出新功能建議 (Feature Request)，或是直接提交 Pull Request。

1. Fork 本專案
2. 建立你的特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交你的修改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 開啟一個 Pull Request

---

## 📄 開源協議

本專案採用 [MIT License](LICENSE) 協議開源。
