# 𝗚𝗹𝗢𝗥𝗶𝗔'𝘀 𝗨𝗻𝗶𝗰𝗼𝗱𝗲
<img width="1214" height="557" alt="glorias_unicode_website" src="https://github.com/user-attachments/assets/f7f87e70-a348-4c09-a9ce-9d647bf14b6f" />

> A pure-Unicode kaomoji creation tool in the making, starting from the building blocks.

🔗 **Live Demo:** https://imglorialiu.github.io/glorias-unicode/

📖 **中文版說明請見下方 / [Jump to Chinese README](#-中文版說明)**

---

## ✨ What is this?

Have you ever wanted to add a little flair to your posts, messages, or usernames, only to find that:

- Emojis look different on Windows vs. Mac 😩
- Kaomoji tools online are outdated, messy, and uncategorized 😵
- You want to build your own ٩(◕‿◕)۶ but can't find the right symbols?

**GlORiA's Unicode** was created to solve these problems.

This is a work-in-progress tool designed to let anyone:
- 🔍 **Browse** curated pure-Unicode symbols (no display issues across systems)
- 🎨 **Compose** your own kaomoji
- 💾 **Save** favorite symbols and kaomoji
- 📤 **Export / Import** your personalized symbol collections

---

## 🎯 Why Pure Unicode?

This isn't a limitation — it's a deliberate choice:

| Feature | Emoji 😀 | Pure Unicode ✦ |
|---|---|---|
| Cross-platform display | Looks different on Windows / Mac / iOS / Android | **Always looks the same** |
| Style | Commercial, cartoonish | Minimal, retro, design-friendly |
| Kaomoji composition | Not possible | **Free to combine** |

Every symbol in the database is **manually curated**. Anything that doesn't render consistently across systems is filtered out.

> Currently tested on Mac and Android. Full Windows testing is in progress.

---

## 🎨 Features

### Currently Available
- ✅ 30+ categories of curated Unicode symbols (ancient scripts, modern languages, technical symbols, writing systems, etc.)
- ✅ Favorites system (save symbols you love)
- ✅ Custom categories (build your own symbol sets)
- ✅ Manual symbol entry
- ✅ Category pack export / import (community sharing)
- ✅ Responsive design (mobile, tablet, desktop)

### Design Principles
- 🚫 **No ads, non-commercial**
- 🚫 **No tracking, no personal data collected**
- ✅ **Pure frontend, open source**
- ✅ **User-centric categorization** (not just copying Unicode official blocks)

---

## 🗺️ Roadmap

This project is just getting started. The symbol library is just the **appetizer** — the real main course is the kaomoji tool.

### Short-term
- [ ] Symbol search (by keyword, by context)
- [ ] Kaomoji composition interface (drag-and-drop from the symbol library)
- [ ] Default kaomoji library (a curated set designed by the author)

### Mid-term
- [ ] Cross-platform compatibility tagging (mark which systems each symbol supports)
- [ ] Kaomoji editor (live preview, save)
- [ ] Full Windows environment testing

### Long-term
- [ ] Contextual recommendations (kaomoji combinations for birthdays, comfort, celebrations, etc.)
- [ ] Community co-creation (users upload their own kaomoji designs)

---

## 📦 Data Structure

All symbol data is stored as JSON files under `data/unicode/`, categorized by theme:

```
data/unicode/
├── _index.json              # Master index
├── arrows.json              # Arrows
├── currency.json            # Currency symbols
├── math-operators.json      # Math operators
├── ancient-greek-aegean.json # Ancient Greek / Aegean scripts
├── braille.json             # Braille
├── ipa-phonetic.json        # IPA phonetic
└── ... (30+ categories)
```

Feel free to open an Issue or PR to suggest new categories, add symbols, or report cross-platform display issues!

---

## 🛠️ Technical Notes

### Why JSON-based file separation?

Initially, I considered putting all symbols directly into `index.html`. But I quickly realized:
**Cramming thousands of symbols into a single HTML file would slow down initial load, freeze the browser, and become a maintenance nightmare.**

So I went with this architecture:

```
index.html              ← UI and interaction logic (HTML + CSS + JS)
└── data/unicode/
    ├── _index.json     ← Master index
    ├── arrows.json     ← Arrows category
    ├── greek.json      ← Greek script
    └── ... (30+ categories)
```

Each category lives in its own JSON file, and **only the JSON for the category the user clicks gets loaded**.

### Benefits of this design

- ⚡ **Fast initial load**: Only the index loads upfront, not all data at once
- 🧩 **Easy to extend**: Adding a category = adding a JSON file, no HTML changes needed
- 🔍 **Future-ready for search**: Structured data enables keyword and context-based search
- 🤝 **Lower contribution barrier**: Want to add symbols? Just edit a JSON file — no need to touch code

### 🛡️ Security Design

Because this tool supports **"import category packs"** and **"custom symbols"** features, it receives external data. To prevent malicious content from causing XSS (Cross-Site Scripting) attacks, all user-facing data goes through an `esc()` function for escaping:

```javascript
// Convert dangerous characters to HTML entities so browsers don't execute them as code
'<' → '&lt;'
'>' → '&gt;'
'"' → '&quot;'
```

**Protection scope:**
- ✅ All user data read from `localStorage`
- ✅ External JSON data loaded via import
- ✅ Display of custom category names and custom symbols

This tool collects no personal data and sends nothing to any server, but since it supports importing, **it has a responsibility to ensure users aren't attacked by malicious files**.

### Architecture Highlights

- 🪶 **Single-file frontend**: Aside from JSON data, the entire frontend is a single `index.html`
- 🚫 **Zero dependencies**: No React, Vue, or jQuery — just vanilla HTML/CSS/JS
- 📦 **No build step**: Copy the files and it runs; open in a browser and it works
- 🌐 **Pure static**: Deployable on any free hosting service

### Why these choices?

This architecture reflects the project's core philosophy:
> **"Lowering the barrier" — so anyone who wants to contribute can read, modify, and deploy this project directly.**

---

## 🤖 About the Developer

I'm GlORiA, and I have **no frontend engineering background**.

This project is an experiment I built from scratch using AI tools (Claude, Cursor, etc.). I want to prove one thing:

> **"Without an engineering background, you can still use AI to build open-source tools that are functional, useful, and secure."**

I'm currently applying to the [OpenAI Codex for Open Source](https://developers.openai.com/codex/codex-for-oss) program to further explore how AI tools can lower the barrier to open-source contribution. If you're curious about the same question, feel free to Star ⭐ this project and follow along.

---

## 📄 License

MIT License — Free to use, modify, and distribute. Please keep the author attribution.

---

## 🙏 Acknowledgements

- The Unicode Consortium, whose standards made this project possible
- All AI-assisted development tools that enable non-engineers to participate in open source
- Everyone who contributes via Issues or PRs ❤️

---
---

# 📖 中文版說明

> 一個正在打造的純 Unicode 顏文字創作工具,從零件庫開始。

🔗 **線上體驗:** https://imglorialiu.github.io/glorias-unicode/

---

## ✨ 這是什麼?

你有沒有過這種經驗——想在貼文、訊息、暱稱裡加一點特別的裝飾,但:

- Emoji 在 Windows 跟 Mac 上長得不一樣 😩
- 網路上找到的顏文字工具又老又雜,根本沒分類 😵
- 想自己組一個 ٩(◕‿◕)۶ 卻不知道那些符號要去哪找

**GlORiA's Unicode** 就是為了解決這些困擾而生的。

這是一個正在開發中的工具,目標是讓任何人都能:
- 🔍 **瀏覽**精選過的純 Unicode 符號(不用擔心顯示問題)
- 🎨 **組裝**自己的顏文字
- 💾 **收藏**喜歡的符號和顏文字
- 📤 **匯出/匯入**自己的個人化符號集

---

## 🎯 為什麼是純 Unicode?

這不是限制,是**刻意的選擇**:

| 特性 | Emoji 😀 | 純 Unicode ✦ |
|---|---|---|
| 跨系統顯示 | Windows / Mac / iOS / Android 長得都不一樣 | **永遠長一樣** |
| 風格 | 商業化、卡通 | 文藝、復古、有設計感 |
| 顏文字組裝 | 不可能 | **可以自由組合** |

每一個收錄到資料庫的符號,都經過**人工篩選**,無法跨系統正常顯示的一律過濾掉。

> 目前已在 Mac 與 Android 上實測,Windows 環境的全面測試進行中。

---

## 🎨 功能特色

### 目前已有
- ✅ 30+ 個分類的精選 Unicode 符號庫(古文字、現代語言、技術符號、書寫系統等)
- ✅ 收藏功能(儲存喜歡的符號)
- ✅ 自訂分類(建立自己的符號集)
- ✅ 手動新增符號
- ✅ 分類包匯出 / 匯入(社群分享)
- ✅ 響應式設計(手機、平板、桌機通用)

### 設計理念
- 🚫 **無廣告、非營利**
- 🚫 **不追蹤、不收個資**
- ✅ **純前端、開源**
- ✅ **以使用者認知為核心的分類**(不是照搬 Unicode 官方 block)

---

## 🗺️ Roadmap

這個專案才剛開始。符號庫只是**前菜**,真正的主菜是顏文字工具。

### 短期
- [ ] 符號搜尋功能(按關鍵字、按情境)
- [ ] 顏文字組裝介面(從符號庫拖拉零件)
- [ ] 預設顏文字庫(作者親自設計的精選集)

### 中期
- [ ] 跨系統相容性標記(每個符號標註支援的系統)
- [ ] 顏文字編輯器(即時預覽、儲存)
- [ ] Windows 環境全面測試

### 長期
- [ ] 情境化推薦(生日、安慰、慶祝等情境的顏文字組合)
- [ ] 社群共創(使用者上傳自己設計的顏文字)

---

## 📦 資料結構

所有符號資料以 JSON 格式儲存在 `data/unicode/` 目錄,依主題分類:

```
data/unicode/
├── _index.json              # 總索引
├── arrows.json              # 箭頭
├── currency.json            # 貨幣符號
├── math-operators.json      # 數學運算子
├── ancient-greek-aegean.json # 古希臘 / 愛琴海文字
├── braille.json             # 點字
├── ipa-phonetic.json        # 國際音標
└── ... (30+ 個分類)
```

歡迎開 Issue 或 PR 提議新的分類、符號補充,或回報跨系統顯示問題!

---

## 🛠️ 技術說明

### 為什麼用 JSON 分檔?

最初我想過把所有符號直接寫進 `index.html`,但很快就意識到:
**幾千個符號塞進一個 HTML,會讓首次載入變慢、瀏覽器卡頓,未來也難以維護。**

於是改成這樣的架構:

```
index.html              ← 介面與互動邏輯(HTML + CSS + JS)
└── data/unicode/
    ├── _index.json     ← 總索引
    ├── arrows.json     ← 箭頭分類
    ├── greek.json      ← 希臘文字
    └── ... (30+ 個分類)
```

每個分類獨立一個 JSON 檔,**使用者點哪個分類,才載入那個 JSON**。

### 這樣設計的好處

- ⚡ **首次載入快**:只載入索引,不會一次吞下所有資料
- 🧩 **易擴展**:新增分類 = 加一個 JSON 檔,不用改 HTML
- 🔍 **未來能做搜尋**:結構化資料才能做關鍵字、情境搜尋
- 🤝 **降低貢獻門檻**:想補符號的人,只要編輯 JSON 就好,不用碰程式碼

### 🛡️ 安全性設計

因為這個工具支援「**匯入分類包**」和「**自訂符號**」功能,會接收外部資料。為了避免惡意內容造成 XSS 跨站腳本攻擊,所有顯示到畫面上的資料都會經過 `esc()` 函式轉義:

```javascript
// 將危險字元轉成 HTML 實體,避免被瀏覽器當成程式碼執行
'<' → '&lt;'
'>' → '&gt;'
'"' → '&quot;'
```

**保護範圍:**
- ✅ 從 `localStorage` 讀取的所有使用者資料
- ✅ 匯入功能讀取的外部 JSON 資料
- ✅ 自訂分類名稱、自訂符號的顯示

這個工具不收個資、不送資料到任何伺服器,但既然支援匯入功能,**就有責任確保使用者不會被惡意檔案攻擊**。

### 架構特色

- 🪶 **單檔前端**:除了 JSON 資料,整個前端就是一個 `index.html`
- 🚫 **零依賴**:不用 React、Vue、jQuery,純原生 HTML/CSS/JS
- 📦 **無需 build**:複製檔案就能跑、瀏覽器直接打開就能用
- 🌐 **純靜態**:可部署在任何免費託管服務

### 為什麼這樣選?

這個架構選擇符合本專案的核心精神:
> **「降低門檻」——讓任何想參與的人,都能直接讀懂、修改、部署這個專案。**

---

## 🤖 關於開發者

我是 GlORiA,**沒有前端工程背景**。

這個專案是我用 AI 工具(Claude、Cursor 等)從零開始打造的實驗。我想證明一件事:

> **「沒有工程背景,也可以用 AI 把開源工具做到能用、好用、安全的程度。」**

目前正在申請 [OpenAI Codex for Open Source](https://developers.openai.com/codex/codex-for-oss) 計畫,希望進一步驗證 AI 工具如何降低開源貢獻的門檻。如果你有同樣的好奇,歡迎 Star ⭐ 追蹤這個專案的進展。

---

## 📄 License

MIT License — 自由使用、修改、散布,但請保留作者 GlORiA 資訊。

---

## 🙏 致謝

- Unicode Consortium,因為有他們的標準,這個專案才有可能
- 所有 AI 輔助開發工具,讓非工程背景的人也能參與開源
- 每一個用 Issue 或 PR 幫忙這個專案的人 ❤️
