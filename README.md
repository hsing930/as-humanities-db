# 中央研究院 人文社會科學數位資料庫導覽與智能選庫系統

本專案整合中央研究院人文社會科學組 **12 個研究所與研究中心、數位文化中心以及南部院區** 的 40 個專業原典資料庫，並提供依研究領域分類、教材轉化指引與 **「研究課題智能選庫助手」** 功能。

## 🌟 核心特色
1. **40 個官方原典資料庫**：涵蓋商周考古 3D 文物、明清官僚檔案、臺灣史古文書、百年歷史疊圖 GIS、六朝小說疾病地圖、社會變遷抽樣數據及法政經濟期刊。
2. **研究課題智能選庫（AI Advisor）**：師生輸入研究題目（如日治教育、家鄉百年地貌、古代疫情偏方），自動推薦首選起手資料庫與三階段研究路徑。
3. **每日自動化巡檢維護（GitHub Actions）**：內建自動化排程，每天早上 9:00（台灣時間）自動發送 HTTP 請求測試全庫 40 個網址，一旦斷鏈即時自動開 Issue 警示。
4. **單一頁面無依賴**：完全前端自包含架構，手機、平板、電腦皆可流暢開啟。

---

## 🚀 部署教學（不到 1 分鐘快速上線）

### 方式一：GitHub 網頁直接上傳（免裝 Git，最快）
1. 在 GitHub 建立一個新的公開倉庫（Repository），命名為例如 `as-humanities-databases`。
2. 將本專案的所有檔案（`index.html`、`README.md`、`.github/` 資料夾、`scripts/` 資料夾）拖曳上傳至倉庫的 `main` 分支根目錄。
3. 進入倉庫的 **Settings** ➔ **Pages**。
4. 在 **Build and deployment** 底下的 **Source** 選擇 **GitHub Actions**（或選擇 `Deploy from a branch` ➔ 選擇 `main` 分支與 `/ (root)`）。
5. 點擊 **Save**，約 30 秒後即可在上方看到您的專屬公開網址：
   `https://<你的GitHub帳號>.github.io/as-humanities-databases/`

### 方式二：使用 Git 命令列推送 
```bash
git init
git add .
git commit -m "Initial commit: Academia Sinica Humanities Databases Hub"
git branch -M main
git remote add origin https://github.com/<你的GitHub帳號>/<你的倉庫名稱>.git
git push -u origin main
```

---

## ⏰ 每日自動巡檢維護機制 (GitHub Actions)
* **執行排程**：每週一至週日，台灣時間每日上午 09:00 (`0 1 * * *` UTC)。
* **檢查腳本**：`scripts/check_links.py`。
* **異常報警**：若中研院某資料庫因伺服器維護或更換網址而回傳錯誤，GitHub Actions 會自動建立標記為 `broken-link` 的 Issue，並透過 Email 寄送通知。
* **手動執行**：亦可隨時在 GitHub 倉庫的 **Actions** 頁面點選 `Daily Academia Sinica Link Checker` ➔ 點擊 **Run workflow** 進行即時巡檢。

---

## 📄 授權與宣告
本專案為學術與歷史教育推廣用途，各數位資料庫與史料之著作權與數位影像權利均歸屬**中央研究院**及各典藏所屬單位所有。
