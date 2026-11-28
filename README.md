# 使用說明

## 一、上線（只要做一次）

1. 到 GitHub 建一個新的 repo，名稱取為 `你的帳號.github.io`，網址會最單純。
2. 把這個資料夾裡的所有檔案上傳到 repo。在 repo 頁面按「Add file → Upload files」，直接拖進去就行。
3. 到 repo 的 **Settings → Pages**，把 Source 設成 `Deploy from a branch`，Branch 選 `main`、資料夾選 `/ (root)`，按 Save。
4. 等一兩分鐘，打開 `https://你的帳號.github.io` 就能看到網站。
5. 在 **Settings → Collaborators** 把另一位作者加進來，對方接受邀請後就能發文。

> 如果 repo 不是取名為 `帳號.github.io`，請把 `_config.yml` 裡的 `baseurl` 改成 `"/repo名稱"`。

## 二、發一篇新文章

1. 先上傳封面圖：進入 `images` 資料夾，按「Add file → Upload files」。
2. 進入 `_posts` 資料夾，按「Add file → Create new file」。
3. 檔名用這個格式：`年-月-日-英文短名.md`，例如 `2026-12-01-my-toys.md`。
4. 內容照著下面的樣子寫：

```
---
title: "第2回「標題」 / English Title"
author: 你的名字
cover: /images/你的圖.jpg
excerpt_en: "首頁標題下方那行英文短句（可省略）"
---

第一段中文……

<!-- English -->

First English paragraph...

<!-- row -->

![共用圖片說明 / Caption](/images/圖.jpg)

<!-- row -->

第二段中文……

<!-- English -->

Second English paragraph...
```

5. 按「Commit changes」，大約一分鐘後首頁就會出現這篇。

## 三、小技巧

- 段落之間空一行。
- `## 小標題` 會顯示成黃色的小標題。
- 文章由好幾「列」組成，每列之間用單獨一行 `<!-- row -->` 隔開。
- 一列裡用單獨一行 `<!-- English -->` 隔開中英文：電腦版左中文、右英文並排對齊；手機版出現「中文・English」切換按鈕。
- 沒有 `<!-- English -->` 的列會橫跨兩欄，適合放中英文共用的圖片，手機上兩種語言都看得到。
- 只屬於某個語言的圖片，直接放在那一側的文字裡就好。
- 標記的大小寫和空格都要完全一樣。整篇都沒有 `<!-- English -->` 的話，文章會顯示成單欄。
- 在內文放圖片：`![說明](/images/圖檔名.jpg)`
- 指定圖片大小（只影響電腦版）：在圖片後面緊接著加標記，中間不要空格
  - `{: .s}` 小（滾動框的 1/4）、`{: .m}` 中（1/3）、`{: .l}` 大（1/2）、`{: .xl}` 特大（2/3）
  - `{: style="width: 280px"}` 自訂寬度
  - 例：`![雷達站](/images/radar.jpg){: .l}`
  - 沒加標記的圖片照原圖大小，最寬 1/3
- 要改顏色或字型，請改 `style.css`。網站名稱和介紹文字在 `_config.yml`。

## 四、檔案結構：要改什麼去哪裡

| 檔案 | 負責的部分 |
|---|---|
| `_config.yml` | 網站標題、副標題、ABOUT 框的白字 |
| `_layouts/default.html` | 所有頁面共用的外框：頁首、ABOUT 框（含粉紅那行）、滾動框、TOP、頁尾 |
| `_layouts/post.html` | 文章內頁：中英對照的排法、手機版語言切換按鈕 |
| `index.html` | 首頁：「最新文章」標題和每篇文章的卡片 |
| `archive.html` | 文章列表頁：表格內容、每幾篇共用一張圖（`per`） |
| `style.css` | 所有顏色、字型、大小、框線。檔案開頭有目錄，分成 9 區 |
| `_posts/` | 文章 |
| `images/` | 圖片 |

**改顏色：** 打開 `style.css`，最上面「1. 色彩與框線設定」那一區就是全站的顏色，改一次全站都會跟著變。
