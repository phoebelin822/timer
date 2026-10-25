# timer數數計時器

## 專案發起與原始交付需求 (Project Brief)

- **專案名稱**：timer數數計時器
- **發起時間**：2026-10-25
- **設計/技術規範**：原生 HTML5 / CSS3 / Vanilla JavaScript、Web Audio API、Web Speech API、Screen Wake Lock API、PWA (Service Worker + Manifest)、GitHub Pages 靜態架構
- **來源資料**：`https://github.com/phoebelin822/timer`
- **原始任務目標與交付文字**：
> https://github.com/phoebelin822/timer

---

## 專案概述

數數計時器是一套專為運動、復健、冥想或固定間隔計數設計的高精準計時網頁應用。核心特色為每 10 秒進行動態語音報數（第 10s 報「1」、第 30s 報「2」、第 50s 報「3」...），並於每 20 秒交替播放清脆提示音，免除運動過程中需隨時低頭看螢幕的困擾。

---

## 核心功能與升級特色

1. **核心報數邏輯**：
   - 每 10 秒判定一次週期。
   - 奇數十秒（10s, 30s, 50s...）：語音朗讀累計報數（1, 2, 3...）。
   - 偶數十秒（20s, 40s, 60s...）：合成清脆雙音階提示音。
   - 每秒可選滴答微聲（可一鍵開關）。
   - 完成時播放和弦收尾音。

2. **高精準背景計時核心**：
   - 內建 Web Worker 獨立線程計時，防止行動裝置瀏覽器因切換分頁或進入待機而發生計時延遲與節流問題。

3. **防休眠螢幕常亮 (Screen Wake Lock)**：
   - 啟動計時自動鎖定螢幕常亮，防止訓練期間手機自動鎖定黑屏；暫停或重置時自動釋放喚醒鎖。

4. **現代化視覺設計與互動**：
   - 沉浸式暗色模式與動態 SVG 環形進度指示。
   - 快速預設時長按鈕（3 分、5 分、10 分、15 分、20 分）。
   - 當前報數狀態動態微脈衝呼吸效果。
   - 支援暫停、繼續、重置完整控制流程與觸覺震動回饋。

5. **PWA 離線應用支援**：
   - 具備完整 `manifest.json` 與 `sw.js` (Service Worker)。
   - 支援 iOS Safari「加入主畫面」與 Android 獨立 App 模式安裝，無網路亦可離線運行。

6. **GitHub Pages 即開即用**：
   - 根目錄包含標準 `index.html` 與相容 `timer.html`，啟用 GitHub Pages 即可直接部署上線。

---

## 目錄結構

```text
├── index.html        # 主應用入口 (支援 GitHub Pages 預設加載)
├── timer.html        # 相容入口文件
├── manifest.json     # PWA 應用設定檔
├── sw.js             # Service Worker 離線快取腳本
├── icons/            # PWA 高解析度圖標
│   ├── icon-192.png
│   └── icon-512.png
└── README.md         # 專案說明與規範文件
```

---

## 本地測試與運行

無需任何建置步驟，可直接以瀏覽器開啟 `index.html`，或使用靜態伺服器：

```bash
# 使用 Python 啟動本機伺服器
python3 -m http.server 8080
```

開啟瀏覽器前往：`http://localhost:8080`
