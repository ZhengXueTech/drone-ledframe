# 足球無人機燈框工具箱

新北市立中正國民中學創客社的足球無人機燈框工具。全部是單一 HTML 檔，不用安裝，電腦和手機都能用。

網址：`https://zhengxuetech.github.io/drone-ledframe/`

## 工具
| 檔案 | 說明 |
|---|---|
| `ledframe.html` | 燈框設計器：選無人機 → 選尾燈樣式 → 微調 → 下載 STL。學生預設是 4 步簡易模式；老師按右上角「學生模式」輸入密碼切換老師模式。 |
| `stl-viewer.html` | STL 檢視器：開 STL／zip、看尺寸、估重量、檢查封閉、剖面、量距離。 |

## 以後怎麼更新（只要改 tools.json）
- **更新某個工具**：把新的 HTML 覆蓋同一個檔名上傳，然後在 `tools.json` 改它的 `version`、`updated`，在 `news` 最上面加一行。
- **新增工具**：把 HTML 上傳，然後在 `tools.json` 的 `tools` 加一段：
  ```json
  { "id": "新的代號", "name": "工具名稱", "file": "檔名.html", "icon": "tool",
    "version": "1.0", "updated": "2026-11-01", "status": "測試中",
    "tags": ["學生"], "desc": "一句話說明", "steps": ["第一步", "第二步"] }
  ```
  - `icon` 可以用：`frame`、`cube`、`ruler`、`doc`、`tool`
  - `status` 可以用：`穩定`、`測試中`、`新`
  - 想暫時隱藏：加 `"hidden": true`
- **改公告或標題**：改 `tools.json` 的 `site`。
- 不用改 `index.html`。

## 新增無人機機型（machines.json）
1. 收到量測資料（Google 表單回覆）後，用**老師模式**打開燈框設計器 → ① 機型 →「複製成新機型」→ 填入數字，看 3D 確認圓環和鎖點位置。
2. 按「複製成機型庫格式」，會得到一行像這樣的文字：
   `{"id":"tc200i-7","status":"draft","code":"LFM2-…"}`
3. 打開 `machines.json`，貼進 `machines` 的方括號裡；如果前面已經有別台，前一筆後面要加逗號。
4. 上傳。大家重新整理燈框設計器，就會在「選無人機」看到這台（草稿會標「數字可能不準」）。
5. 試印裝過、確定套得上，把 `"draft"` 改成 `"verified"`。
- `id` 只能用英文小寫、數字、減號，而且不要改（學生存的選擇和設計碼靠它認機型）。
- 想改顯示名稱：加 `"name": "新名稱"`。

## 表單示意圖
`form-images/` 是「無人機機型資料回報」Google 表單用的示意圖，由「表單加圖.gs」自動插進表單。不要刪、不要改檔名。

## 注意
- 老師版檔案（打開就是老師模式）不要放在這裡，只私下傳給老師。
- 老師密碼寫在網頁程式裡，只能擋一般操作，不是資安保護。
- 開啟 GitHub Pages：repo 的 Settings → Pages → Branch 選 `main`、資料夾選 `/ (root)` → Save。
