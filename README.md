# Brython Letter Display (字母顯示器)  
### 這是一個以 Brython（Python for Browser） 撰寫的互動式網頁程式，能將使用者輸入的英文字母或數字，轉換成由 7×7 彩色方格 組成的像素字
(為了這句 A strict teacher produces excellent student，多搞了幾個版本)

<img width="1247" height="846" alt="image" src="https://github.com/user-attachments/assets/36f4b46b-ed41-4c12-8d4b-5065b2bdf9bf" />

 

##  Advanced Brython 字母顯示器功能

互動字母視覺化 – 使用 Brython（瀏覽器中的 Python）動態顯示與動畫化字母

- 即時輸入支援 – 使用者可輸入字母，立即在畫布上呈現

- 可自訂樣式 – 可以調整字型大小、顏色與顯示效果

- 網格佈局 – 字母以結構化的網格系統排列顯示

- 互動控制 – 包含按鈕與滑桿，可控制動畫速度、字母大小與佈局

- 瀏覽器直接運行 – 無需安裝，透過 GitHub Pages 即可使用


  

 ##  運作原理
1️⃣ Brython 與前端結構

Brython 讓 Python 程式可在瀏覽器中運行，取代 JavaScript
HTML 中的 <script type="text/python"> 區塊即是主要邏輯

主要組成部分：

HTML + CSS：定義按鈕、輸入框與顯示區域

Brython：以 Python 控制 DOM、Canvas、按鈕事件
#

2️⃣ 顯示核心（點陣繪製邏輯）

每個字元（如 A, B, 1, 2, …）在字典 LETTER_PATTERNS 中定義
範例：

'A': ["0011100",
      "0110110",
      "1100011",
      "1111111",
      "1100011",
      "1100011",
      "1100011"]


每一行代表 7 個像素點，1 為有色方格，0 為空白
#

3️⃣ World 類別（繪圖世界）

負責建立一個 Canvas「世界」：

有三層：grid（格線）、background（背景）、display（顯示層）

每一格方塊為 25px × 25px。

使用 draw_color_block(x, y, color) 於指定座標畫出有色方格
#

4️⃣ LetterDisplay 類別（顯示控制）

接收輸入文字，依照字數建立對應寬度的繪圖世界

逐字取出 LETTER_PATTERNS 中的資料，依序繪製

每個字元顏色不同，從 self.colors 中循環取色
#

5️⃣ 互動操作

透過 Brython 綁定按鈕與輸入事件：

「顯示」：讀取輸入框內容並呼叫 display.display_text()

「清除」：清空輸入框與顯示區

範例按鈕：快速輸入並顯示預設字串

按下 Enter 鍵也能觸發顯示

##

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e1946f3f-a9b7-4934-b951-7b4b51d10bb5" />




