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

## 注意
- 老師版檔案（打開就是老師模式）不要放在這裡，只私下傳給老師。
- 老師密碼寫在網頁程式裡，只能擋一般操作，不是資安保護。
- 開啟 GitHub Pages：repo 的 Settings → Pages → Branch 選 `main`、資料夾選 `/ (root)` → Save。
