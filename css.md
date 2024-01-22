---
description: ページの一部をアクセスさせたくない場合のスタイルシート対応
---

# CSS

例：[https://codepen.io/edkw-the-decoder/pen/jOJwvgo](https://codepen.io/edkw-the-decoder/pen/jOJwvgo)

HTML

```html
<div class="parent">
  <div class="content">
    <div class="box">
      <p class="message">
        テストメッセージ１<br>
        テストメッセージ２<br>
        テストメッセージ３
      </p>
    </div>
  </div>
  <input type="text" value="test">
  <button name="test_button">ボタン</button>
</div
```

CSS

```css
.parent {
  margin: 50px;
  position: relative;
  height: 200px;
  padding: 20px;
}

.content {
  display: block;
  position: absolute;
  top: 0px;
  left: 0px;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);

  /* 子要素を水平方向の中央に配置する */
  display: flex;
  justify-content: center;
}

.box {
  width: 30%;
  height: 100px;
  background: green;
  /* 水平・垂直方向の中央揃え */
  position: absolute;
  top: 40px;
}

.message {
  font-size: 1em;
  color: #fff;
  text-align: center;
  line-height: 1.4em;
  padding: 0px;
}

```
