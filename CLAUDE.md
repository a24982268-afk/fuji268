# 蹦火仔 預約網站 — 給 Claude 的專案說明

客人用的公開網頁（GitHub Pages：https://a24982268-afk.github.io/fuji268/）。介面與回覆一律繁體中文、手機優先。

- `index.html`：遊程介紹與預約詢問表單。產生「【蹦火仔 預約詢問】」文字，按「用 LINE 傳送」帶進 @FUJI268 聊天室，
  接團台的 LINE 機器人會解析這段文字建立團單——**欄位名稱與格式改了，要同步改 `fuji268-desk/apps-script/Code.gs` 的 `parseInquiry_`
  和接團台 `index.html` 的 `parse`**。選海上類遊程與日期時，向接團台後端 `?avail=1` 查名額（只拿得到 open/few/full/stop/none）。
- `pax.html`：客人用專屬連結（`?b=團單&k=金鑰`）填旅客名單，送到後端 `paxSubmit`。會檢查身分證字號與日期格式。

整套系統（接團台、後端、LINE 機器人、資料欄位、必守規則、測試工具）的說明在 `a24982268-afk/fuji268-desk` 的 `CLAUDE.md`
與 `.claude/skills/desk-change/SKILL.md`，修改前先讀。兩個網頁共用同一個後端網址（`AKfycbyl_kkW…/exec`）。
