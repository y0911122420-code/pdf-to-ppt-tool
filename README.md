# PDF 轉 PPT 工具

免費線上 PDF 轉 PPT（.pptx）工具，純前端、無後端伺服器：
上傳的 PDF 完全在瀏覽器裡用 [pdf.js](https://mozilla.github.io/pdf.js/) 解析、
把每一頁畫成圖片，再用 [PptxGenJS](https://gitbrent.github.io/PptxGenJS/) 組成
`.pptx` 檔案讓使用者下載，檔案不會上傳到任何伺服器。

## 使用方式

直接用瀏覽器開啟 `index.html`（或部署到任何靜態網站託管服務，例如 GitHub Pages）。

本機開發可用任何靜態伺服器，例如：

```bash
python3 -m http.server 8080
# 開瀏覽器打開 http://localhost:8080/
```

## 技術限制

轉出的每一張投影片是該頁 PDF 的圖片（畫面與原 PDF 一致），**圖片裡的文字無法
在 PowerPoint 中直接編輯**。如果需要可編輯文字的簡報，需要另外用文字擷取工具
處理，本工具僅適合「保留原始排版、直接簡報放映」的情境。

## 第三方函式庫

專案內 `vendor/` 目錄自帶以下函式庫（vendored，避免依賴外部 CDN）：

- `vendor/pdfjs/` — [pdf.js](https://github.com/mozilla/pdf.js) 3.11.174（Apache-2.0）
- `vendor/pptxgenjs/` — [PptxGenJS](https://github.com/gitbrent/PptxGenJS) 3.12.0（MIT，內含 JSZip）
