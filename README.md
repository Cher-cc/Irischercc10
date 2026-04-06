# 個人作品集網站修改說明

這個網站是用最簡單、最好維護的方式做的：

- `index.html`：放網站內容文字
- `style.css`：控制顏色、字體、排版
- `script.js`：放一點點互動功能，目前只有手機選單和年份

如果你是零基礎，先記住一件事就好：
平常要改「文字內容」，大多只需要改 `index.html`。

## 1. 怎麼改首頁文字

打開 [index.html](E:\my-portfolio-site\index.html)，找到這一段：

```html
<h1>用漫畫、插畫與動畫，收藏故事裡的色彩與情緒。</h1>
```

你可以直接把中間的文字改成你自己的標題，例如：

```html
<h1>你好，我是小雨，這裡是我的漫畫與插畫作品集。</h1>
```

首頁簡介也可以直接改：

```html
<p class="hero-text">
  這裡展示我的漫畫作品、插畫作品、小說作品與動畫作品。
</p>
```

## 2. 怎麼改作品資料

每一個作品卡片都長得像這樣：

```html
<article class="work-card">
  <div class="work-cover placeholder">漫畫封面</div>
  <div class="work-content">
    <p class="work-date">2026.03.12</p>
    <h3>雨後的信號</h3>
    <p>這裡是作品簡介。</p>
    <a class="text-link" href="#">查看作品</a>
  </div>
</article>
```

你可以改的地方：

- `2026.03.12`：改成發布日期
- `雨後的信號`：改成作品名稱
- `這裡是作品簡介。`：改成作品介紹
- `查看作品`：可以改成你想顯示的字

## 3. 怎麼新增一個作品

最簡單的做法：

1. 在 `index.html` 找到你要新增的區塊，例如 `漫畫區`
2. 複製一整個 `<article class="work-card"> ... </article>`
3. 貼到下一個作品下面
4. 改成你的新作品內容

這樣就完成了。

小說區也是一樣的改法，你只要找到：

```html
<section class="section" id="novels">
```

然後修改裡面的作品卡片內容就可以。

## 4. 怎麼改關於我

找到 `關於我` 區塊，裡面有兩段文字：

```html
<section class="section" id="about">
```

往下看你會找到：

```html
<p>
  我是一位專注於漫畫、插畫、小說與動畫創作的創作者...
</p>
```

把這段換成你自己的自我介紹就可以。

## 5. 怎麼改聯絡方式

找到這一段：

```html
<ul class="contact-list">
  <li>Email: yourname@example.com</li>
  <li>Instagram: @youraccount</li>
  <li>Behance / YouTube / Vimeo: 可替換成你的作品平台</li>
</ul>
```

直接把裡面的內容換成你的資訊。

## 6. 怎麼換圖片

目前這版先用文字區塊代替圖片，方便你先整理內容。

之後你可以把圖片放進：

- `assets/images`

之後再把原本這種區塊：

```html
<div class="work-cover placeholder">漫畫封面</div>
```

改成：

```html
<div class="work-cover">
  <img src="assets/images/你的圖片名稱.jpg" alt="作品名稱封面">
</div>
```

注意：

- `你的圖片名稱.jpg` 要跟資料夾裡的檔名一模一樣
- 建議檔名用英文，例如 `summer-story-cover.jpg`

## 7. 怎麼改顏色

如果之後你想微調網站配色，打開 [style.css](E:\my-portfolio-site\style.css)，最上面會看到這些：

```css
:root {
  --bg: #fdf5f6;
  --accent: #f2aeb4;
}
```

這些是網站主要顏色。
你只要改 `#` 開頭的色碼，就能換整體色調。

## 8. 建議你怎麼維護

最適合新手的順序是：

1. 先只改 `index.html` 的文字
2. 再把圖片放進 `assets/images`
3. 最後如果想微調風格，再改 `style.css`

如果你怕改壞，可以每次修改前先備份一份，例如：

- `index-backup.html`
- `style-backup.css`

## 9. 下一步我可以幫你做什麼

如果你要，我下一步可以直接幫你做下面其中一個：

1. 幫你把每個作品做成可點進去的獨立作品頁
2. 幫你加上真實圖片展示版型
3. 幫你把聯絡方式做成可直接點擊的按鈕
4. 幫你把整個網站內容換成你的真實資料

## 10. 怎麼放到 GitHub Pages

這個網站現在已經是 GitHub Pages 相容的純靜態網站了。

你目前的檔案結構這樣就可以：

- `index.html`
- `style.css`
- `script.js`
- `assets/`

我另外幫你加了：

- `.nojekyll`

這個檔案可以避免 GitHub Pages 把某些檔案當成 Jekyll 專案處理。

### 最簡單的發佈方式

1. 把整個資料夾上傳到 GitHub Repository
2. Repository 裡要看得到 `index.html`
3. 到 GitHub 的 `Settings`
4. 找到 `Pages`
5. 在 `Build and deployment` 選：
   - `Source: Deploy from a branch`
   - `Branch: main`
   - `Folder: / (root)`
6. 存檔後等幾分鐘，GitHub 就會產生網站網址

### 你的網站網址通常會長這樣

```text
https://你的帳號.github.io/你的專案名稱/
```

例如：

```text
https://myname.github.io/my-portfolio-site/
```

### 上傳前要注意

- `index.html` 一定要放在最外層
- 圖片路徑要像這樣寫：

```html
<img src="assets/images/cover.jpg" alt="作品封面">
```

- 不要寫成電腦本機路徑，例如：

```html
<img src="C:\Users\你的名字\Desktop\cover.jpg">
```

這種寫法放到 GitHub Pages 會失效

### 如果你之後有自己的網域

之後也可以再加：

- `CNAME`

不過現在先不用，先讓網站成功上線最重要。
