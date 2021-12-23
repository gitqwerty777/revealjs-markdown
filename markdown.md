# Reveal.js Markdown Demo

---

## Reveal.js

- [Reveal.js](https://revealjs.com)可以使用html或markdown來製作簡報
- 本篇以markdown為主，需要自訂的部份才會用html
- 需搭配[原始碼](https://github.com/gitqwerty777/revealjs-markdown/raw/gh-pages/markdown.md)觀看

---

## 垂直簡報

- 簡報有上下層級
- `Space`鍵: 下一張投影片

-----

## 地下一層

適合作為上層簡報的額外說明

-----

## 地下二層

也可以按方向鍵瀏覽簡報

---

## Markdown 語法

-----

## 條列清單

- 條目
- 條目

1. 列點1
2. 列點2

-----

# 標題1
## 標題2
### 標題3
#### 標題4
##### 標題5
###### 標題6

-----

## 表格

| 模型      | auc  | batch_size | epoch_num | Time of each epoch |
| --------- | ---- | ---------- | --------- | ------------------ |
| LR        | 0.77 | 1024       | 2         | 約30分             |
| FM        | 0.78 | 4096       | 10        | 約2.5小時          |
| FFM       | 0.79 | 4096       | 10        | 約14.3小時         |
| wide_deep | 0.79 | 512        | 4         | 約2小時            |

-----

## 引用

> 引用文章 <br>
> -- 魯迅

-----

## 程式碼

使用`highlight.js`

```php
    public function foo()
    {
        $foo = array(
            'bar' => 'bar'
        )
    }
```

-----

## 圖片

![External Image](https://s3.amazonaws.com/static.slid.es/logo/v2/slides-symbol-512x512.png)
![Internal Image](./assets/image1.png)

-----

## 內部連結

[回到第三張、第二層的投影片](#/3/2)

-----

## 數學公式

三種可選：`KaTeX`、`MathJax2`, `MathJax3`

$H(p) = -p \log(p)$

---

## 和 Markdown 的不同

- 換行要加`<br>`
- 可以插入`html`語法，如影片
- 可以使用`html`的註解語法設定簡報

<video data-autoplay src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4"></video>

---

## 總覽

- `Esc`: 進入總覽模式
- `Alt`+點擊: 放大簡報(使用zoom.js)
- `B` 或 `.`: 暫停
- `?`: 快捷鍵一覽
- `F`: 全螢幕

---

## 簡報者檢視畫面

按`S`顯示

```js
<aside class="notes">
    簡報者筆記，只有在簡報者檢視畫面看得見
</aside>
```

<aside class="notes">
    簡報者筆記，只有在簡報者檢視畫面看得見
</aside>

---

<!-- .slide: data-state="customstate" -->

## 狀態

設定 `data-state="customstate"`<br>
該張簡報就會有 `customstate` 的 class

```js
/* JS */
Reveal.on( 'customstate', function() {
	alert( '"customstate" has fired' );
} );
```

```css
/* CSS */
.customstate {
    text-shadow: black 0.1em 0.1em 0.2em;
}
```

---

# 設定簡報或元素的class

- `<!-- .slide: xxx -->`
- `<!-- .element: xxx -->`

---

## 分段顯示

[https://revealjs.com/fragments/](https://revealjs.com/fragments/)

<span class="fragment">使用 `fragment` class</span>
<span class="fragment">來</span>
<span class="fragment">分段</span>
<span class="fragment">顯示</span>

-----

## 分段動畫

<p class="fragment grow">grow</p>
<p class="fragment shrink">shrink</p>
<p class="fragment fade-out">fade-out</p>
<p>
    <span style="display: inline-block;" class="fragment fade-right">fade-right, </span>
    <span style="display: inline-block;" class="fragment fade-up">up, </span>
    <span style="display: inline-block;" class="fragment fade-down">down, </span>
    <span style="display: inline-block;" class="fragment fade-left">left</span>
</p>
<p class="fragment fade-in-then-out">fade-in-then-out</p>
<p class="fragment fade-in-then-semi-out">fade-in-then-semi-out</p>
<p>Highlight <span class="fragment highlight-red">red</span> <span
        class="fragment highlight-blue">blue</span> <span
        class="fragment highlight-green">green</span></p>

<p><span class="fragment fade-in">
  <span class="fragment highlight-red">
    <span class="fragment fade-out">
      Fade in > Turn red > Fade out
    </span>
  </span>
</span></p>


---

<!-- .slide: id="transitions" -->
## 轉場動畫

- [無](?transition=none#/transitions)
- [Fade](?transition=fade#/transitions)
- [Slide](?transition=slide#/transitions)
- [Convex](?transition=convex#/transitions)
- [Zoom](?transition=zoom#/transitions)
- [Concave](?transition=concave#/transitions)

-----

<!-- .slide: data-background-transition="zoom" data-background="#4d7e65"-->
## 背景轉場

- 全域(寫在`.html`檔): `Reveal.configure({ backgroundTransition: 'zoom' })`
- 單張簡報 `<!-- .slide: data-background-transition="zoom"-->`

-----

## 動畫順序

`<!-- .element: class="fragment" data-fragment-index="1" -->`

- Item 1 <!-- .element: class="fragment" data-fragment-index="2" -->
- Item 2 <!-- .element: class="fragment" data-fragment-index="1" -->

-----

## 程式碼動畫1

```php [1|3-5]
    public function foo()
    {
        $foo = array(
            'bar' => 'bar'
        )
    }
```

-----

## 程式碼動畫2

```js [|4,8-11|17|22-24]
import React, { useState } from 'react';

function Example() {
    const [count, setCount] = useState(0);

    return (
    <div>
        <p>You clicked {count} times</p>
        <button onClick={() => setCount(count + 1)}>
        Click me
        </button>
    </div>
    );
}

function SecondExample() {
    const [count, setCount] = useState(0);

    return (
    <div>
        <p>You clicked {count} times</p>
        <button onClick={() => setCount(count + 1)}>
        Click me
        </button>
    </div>
    );
}
```

-----

## 自訂動畫

加上`<!-- .slide: data-auto-animate -->`，可以對應下一頁相同`data-id`的元素

<!-- .slide: data-auto-animate -->
<div class="r-hstack justify-center">
    <div data-id="box1"
    style="background: #999; width: 50px; height: 50px; margin: 10px; border-radius: 5px;"></div>
    <div data-id="box2"
    style="background: #999; width: 50px; height: 50px; margin: 10px; border-radius: 5px;"></div>
    <div data-id="box3"
    style="background: #999; width: 50px; height: 50px; margin: 10px; border-radius: 5px;"></div>
</div>

-----

<!-- .slide: data-auto-animate -->
<div class="r-hstack justify-center">
    <div data-id="box1" data-auto-animate-delay="0"
        style="background: cyan; width: 150px; height: 100px; margin: 10px;"></div>
    <div data-id="box2" data-auto-animate-delay="0.1"
        style="background: magenta; width: 150px; height: 100px; margin: 10px;"></div>
    <div data-id="box3" data-auto-animate-delay="0.2"
        style="background: yellow; width: 150px; height: 100px; margin: 10px;"></div>
</div>

-----

<!-- .slide: data-auto-animate -->
<div class="r-stack">
    <div data-id="box1" style="background: cyan; width: 300px; height: 300px; border-radius: 200px;">
    </div>
    <div data-id="box2" style="background: magenta; width: 200px; height: 200px; border-radius: 200px;">
    </div>
    <div data-id="box3" style="background: yellow; width: 100px; height: 100px; border-radius: 200px;">
    </div>
</div>

-----

## 隱含動畫

<!-- .slide: data-auto-animate -->
加上`<!-- .slide: data-auto-animate -->`，不需要`data-id`，只要有新增/移除元素會有動畫
# Implicit

-----

## 隱含動畫
<!-- .slide: data-auto-animate -->
# Implicit
# Animation

-----

## 隱含動畫2
<!-- .slide: data-auto-animate -->

- Mercury
- Jupiter
- Mars

-----

## 隱含動畫2
<!-- .slide: data-auto-animate -->

- Mercury
- Earth
- Jupiter
- Saturn
- Mars

---

## 背景設定

- 單色 `<!-- .slide: data-background="#dddddd"-->`
- 圖片 `<!-- .slide: data-background="image.png"-->`
- 圖片(重複) `<!-- .slide: data-background="image.png" data-background-repeat="repeat" data-background-size="100px"-->`
- 圖片(gif) `<!-- .slide: data-background="image.gif"-->`
- 影片 `<!-- .slide: data-background-video="video.mp4" -->`
- iframe `<!-- .slide: data-background-iframe="https://hakim.se" data-background-interactive -->`

-----

<!-- .slide: data-background="#dddddd"-->
## 單色

-----

<!-- .slide: data-background="assets/image1.png" -->
## 圖片

-----

<!-- .slide: data-background="assets/image1.png"  data-background-repeat="repeat"  data-background-size="100px" -->
## 圖片(重複)

-----

<!-- .slide: data-background="http://i.giphy.com/90F8aUepslB84.gif"-->
## 圖片(gif)

-----

<!-- .slide: data-background-video="https://static.slid.es/site/homepage/v1/homepage-video-editor.mp4" -->
## 影片

-----

<!-- .slide: data-background-iframe="https://hakim.se" data-background-interactive -->

<div
    style="position: absolute; width: 40%; right: 0; box-shadow: 0 1px 4px rgba(0,0,0,0.5), 0 5px 25px rgba(0,0,0,0.2); background-color: rgba(0, 0, 0, 0.9); color: #fff; padding: 20px; font-size: 20px; text-align: left;">
    <h2>Iframe 背景</h2>
</div>

---

## 更換主題

在html中修改css檔案(路徑)

---

## 排版

加上 `r-fit-text` class 以自動調整
<h2 class="r-fit-text">文字大小</h2>

-----

## 重疊元素

<div class="r-stack">
  <img class="fragment fade-out" data-fragment-index="0" src="https://placekitten.com/450/300" width="450" height="300">
  <img class="fragment current-visible" data-fragment-index="0" src="https://placekitten.com/300/450" width="300" height="450">
  <img class="fragment" src="https://placekitten.com/400/400" width="400" height="400">
</div>

-----

## 水平/垂直排列

class `r-hstack` 和 `r-vstack`

<div class="r-hstack">
    <p style="padding: 0.50em; background: #eee; margin: 0.25em">One</p>
    <p style="padding: 0.75em; background: #eee; margin: 0.25em">Two</p>
    <p style="padding: 1.00em; background: #eee; margin: 0.25em">Three</p>
</div>

<div class="r-vstack">
    <p style="padding: 0.50em; background: #eee; margin: 0.25em">One</p>
    <p style="padding: 0.75em; background: #eee; margin: 0.25em">Two</p>
    <p style="padding: 1.00em; background: #eee; margin: 0.25em">Three</p>
</div>

-----

## 圖片外框 + 超連結

<img src="assets/image1.png" width="200">
<a href="#">
  <img class="r-frame" src="assets/image1.png" width="200">
</a>

---

## 其他功能

- [JavaScript API](https://revealjs.com/api/)
- [自動翻頁](https://revealjs.com/auto-slide/)
- [視差背景](https://revealjs.com/backgrounds/#parallax-background)
- [自訂快捷鍵](https://revealjs.com/keyboard/)
- [第三方Plugin](https://github.com/hakimel/reveal.js/wiki/Plugins,-Tools-and-Hardware)

---

## End

- 詳細設定請參考 [本簡報repo](https://github.com/gitqwerty777/revealjs-markdown) 的兩個檔案
  - index.html
  - markdown.md