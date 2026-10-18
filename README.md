# 頁來頁好漫畫書庫

《沉默的代理人》全一回、20 頁繁體中文全彩漫畫，附連續閱讀器。

## 網站與部署
- 正式網站：https://yelaiyehao-comics.onrender.com/
- 閱讀網址：https://yelaiyehao-comics.onrender.com/#read/silent-agents
- 僅使用儲存庫 `wujin-studio/yelaiyehao-comics`，與無燼線香網站分開。
- Render Static Site：`srv-db9iqse1egvs73feiuug`；分支 `main`，提交後自動部署。
- Publish directory：`./dist`
- Build command：

```sh
mkdir -p dist && cp index.html dist/index.html && if [ -d assets ]; then cp -R assets dist/assets; fi && if [ -d comics ]; then cp -R comics dist/comics; fi && if [ -d data ]; then cp -R data dist/data; fi
```

## 檔案
- `index.html`：首頁版面、樣式、作品介紹、閱讀器容器。
- `assets/reader.js`：閱讀器與頁碼、放大、進度記憶。
- `data/comics.json`：作品資料、圖片順序與替代文字摘要。
- `comics/silent-agents/page-01.jpg` 至 `page-20.jpg`：完整單頁圖片。

## 後續修改
修改介面後提交至 main 即會部署。替換漫畫頁面可使用同一路徑；調整內容順序須同步修改作品資料。
新增作品時，新增獨立圖片目錄與資料項目，並擴充首頁卡片及 reader.js 的路由、作品 ID、頁數檢查與進度儲存鍵；目前閱讀器專為本作 20 頁設定。
這是可透過 GitHub 維護的靜態網站，目前沒有登入式內容管理後台。
閱讀進度只存在讀者目前裝置的瀏覽器，不上傳至伺服器。

## 發布檢查
確認作品資料列出的每張圖片存在；部署後開啟閱讀網址，檢查 20 頁、頁碼跳轉、放大閱讀及返回書庫。
