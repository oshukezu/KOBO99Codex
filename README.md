# Kobo 99 元選書行事曆

自動爬取 KOBO 部落格「一週99元書單」文章、解析書單並輸出可訂閱的 `.ics` (iCalendar) 檔案，供 Google 日曆「從網址新增」訂閱。
訂閱資訊：https://calendar.google.com/calendar/ical/u72vcutakmkhahnk8en1q90p3hf0gb98%40import.calendar.google.com/public/basic.ics

## 說明
這個專案會在每週四 07:00（台北時間）執行，也會在 push 到 `main` 時更新資料並部署到 GitHub Pages。首頁會自動依照目前網址產生 Google Calendar 訂閱連結。
`public/events.json` 是累積資料庫。腳本預設會保留既有資料並合併新抓到的選書，所以過去已寫入的歷史資料不會在每週更新時被清掉。

## 如何新增日曆
- 開啟 [Google 日曆](https://calendar.google.com/)
- 點選右上角 齒輪 > 設定
- 左側 一般 > 新增日曆 > 加入日曆網址
- 輸入 
- 點選 新增日曆

## GitHub 設定
1. 建立 GitHub repo，將這個資料夾 push 上去。
2. 到 repo 的 `Settings -> Pages`，將 Build and deployment 的 Source 設為 `GitHub Actions`。
3. 到 `Actions` 手動執行 `Update Kobo 99 Calendar` 一次。若要補歷史資料，可填 `history_start_year`，例如 `2024`；也可填 `history_end_year` 指定結束年份。
4. 打開 GitHub Pages 首頁，點 `Google Calendar 訂閱`。
