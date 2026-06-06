# 苹果范主题（apple）样式规则

> 适合场景：品牌故事、产品介绍、创始人专栏、精品内容
> 风格：极简留白，大字号、无多余装饰、内容即设计
> 调性参考：Apple 官网文案、产品发布页正文

---

## 设计语言

| 属性 | 值 |
|------|------|
| 主色调 | `#1d1d1f`（苹果深黑） |
| 强调色 | `#0071e3`（苹果蓝，仅用于链接、少量引用） |
| 次要文字 | `#6e6e73`（苹果灰） |
| 背景色 | `#ffffff`（纯白） |
| 正文字号 | `17px`（比大多数主题大，体现呼吸感） |
| 行高 | `1.9em` |
| 字间距 | `0.02em` |
| 段间距 | `2em`（大段间距是本主题核心） |
| 字体 | `-apple-system, "PingFang SC", "Helvetica Neue", "Hiragino Sans GB", sans-serif` |

---

## 元素级样式规则

---

### 容器（wrapper）

```html
<section style="
  font-family: -apple-system, 'PingFang SC', 'Helvetica Neue', 'Hiragino Sans GB', sans-serif;
  font-size: 17px;
  line-height: 1.9em;
  letter-spacing: 0.02em;
  color: #1d1d1f;
  word-break: break-word;
  padding: 0 16px;
  background: #ffffff;
">
  <!-- 文章内容 -->
</section>
```

---

### 段落（p）

apple 主题段落**间距极大**，每段之间视觉上是真正的停顿：

```html
<p style="
  margin: 2em 0;
  font-size: 17px;
  line-height: 1.9em;
  color: #1d1d1f;
">段落内容</p>
```

---

### 二级标题（h2）

apple 主题的 h2 是**大字号、无任何装饰线**，标题本身就是设计：

```html
<h2 style="
  font-size: 24px;
  font-weight: 700;
  color: #1d1d1f;
  margin: 3em 0 1em;
  line-height: 1.3;
  letter-spacing: -0.01em;
">标题文字</h2>
```

> `letter-spacing: -0.01em` 微收紧，模拟 Apple 官网大标题字距。

---

### 三级标题（h3）

```html
<h3 style="
  font-size: 19px;
  font-weight: 600;
  color: #1d1d1f;
  margin: 2.5em 0 0.8em;
  line-height: 1.4;
  letter-spacing: -0.005em;
">小节标题</h3>
```

---

### 四级标题（h4）

```html
<h4 style="
  font-size: 17px;
  font-weight: 600;
  color: #1d1d1f;
  margin: 2em 0 0.6em;
">四级标题</h4>
```

---

### 加粗（strong / b）

apple 主题加粗**不改颜色**，用字重区分，极度克制：

```html
<strong style="
  font-weight: 600;
  color: #1d1d1f;
">重要内容</strong>
```

---

### 斜体（em / i）

```html
<em style="
  font-style: italic;
  color: #6e6e73;
">斜体内容</em>
```

---

### 引用块（blockquote）

apple 主题 blockquote 用**大字号居左**，不做任何背景色装饰，只用左侧细线定位：

```html
<blockquote style="
  border-left: 2px solid #0071e3;
  padding: 4px 20px;
  margin: 2.5em 0;
">
  <p style="
    margin: 0;
    font-size: 20px;
    line-height: 1.7em;
    color: #1d1d1f;
    font-weight: 300;
    letter-spacing: -0.01em;
  ">引用内容</p>
</blockquote>
```

> `font-weight: 300` 细字重引用，和正文形成对比，是本主题最有辨识度的细节。

---

### 分节符（代替 `---`）

apple 主题用**大段留白**替代分节线——留白本身就是分节：

```html
<div style="margin: 3.5em 0;"></div>
```

---

### 无序列表（ul / li）

apple 主题列表**去掉圆点**，改用缩进传达层级：

```html
<ul style="
  padding-left: 0;
  margin: 2em 0;
  list-style-type: none;
">
  <li style="
    margin: 1em 0;
    font-size: 17px;
    line-height: 1.9em;
    color: #1d1d1f;
    padding-left: 1.2em;
    position: relative;
  ">
    <span style="
      position: absolute;
      left: 0;
      color: #0071e3;
      font-weight: bold;
    ">—</span>
    列表项内容
  </li>
</ul>
```

---

### 有序列表（ol / li）

```html
<ol style="
  padding-left: 1.8em;
  margin: 2em 0;
  list-style-type: decimal;
">
  <li style="
    margin: 1em 0;
    font-size: 17px;
    line-height: 1.9em;
    color: #1d1d1f;
  ">步骤内容</li>
</ol>
```

---

### 行内代码（code）

```html
<code style="
  font-family: 'SF Mono', 'Courier New', Consolas, monospace;
  font-size: 15px;
  color: #1d1d1f;
  background: #f5f5f7;
  padding: 2px 7px;
  border-radius: 5px;
">代码内容</code>
```

---

### 代码块（pre + code）

```html
<pre style="
  background: #f5f5f7;
  border-radius: 12px;
  padding: 20px;
  margin: 2em 0;
  overflow-x: auto;
  font-size: 14px;
  line-height: 1.7;
"><code style="
  font-family: 'SF Mono', 'Courier New', Consolas, monospace;
  color: #1d1d1f;
  white-space: pre;
  word-break: normal;
">代码内容</code></pre>
```

---

### 表格（table）

```html
<table style="
  width: 100%;
  border-collapse: collapse;
  margin: 2em 0;
  font-size: 15px;
">
  <thead>
    <tr>
      <th style="
        background: transparent;
        color: #6e6e73;
        font-weight: 600;
        padding: 10px 0;
        text-align: left;
        border-bottom: 1px solid #d2d2d7;
        font-size: 13px;
        letter-spacing: 0.05em;
      ">列头</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="
        padding: 12px 0;
        border-bottom: 1px solid #d2d2d7;
        color: #1d1d1f;
      ">内容</td>
    </tr>
    <tr>
      <td style="
        padding: 12px 0;
        border-bottom: 1px solid #d2d2d7;
        color: #1d1d1f;
      ">内容</td>
    </tr>
  </tbody>
</table>
```

---

### 分割线（hr）

```html
<hr style="
  border: none;
  border-top: 1px solid #d2d2d7;
  margin: 3em 0;
">
```

---

### 图片（img）

```html
<figure style="
  text-align: center;
  margin: 2.5em -16px;
">
  <img src="图片URL" alt="图片描述" style="
    max-width: 100%;
    display: block;
    margin: 0 auto;
    border-radius: 12px;
  ">
  <figcaption style="
    font-size: 13px;
    color: #6e6e73;
    margin-top: 10px;
    letter-spacing: 0.02em;
    padding: 0 16px;
  ">图片说明（可选）</figcaption>
</figure>
```

---

### 超链接（a）

```html
<span style="
  color: #0071e3;
">链接文字</span>
<sup style="font-size: 10px; color: #6e6e73;">[1]</sup>
```

---

### 结尾署名区

```html
<div style="
  margin-top: 4em;
  padding-top: 2em;
  border-top: 1px solid #d2d2d7;
">
  <p style="
    margin: 0;
    font-size: 14px;
    color: #6e6e73;
    letter-spacing: 0.03em;
  ">结尾文字</p>
</div>
```

---

## 微信排版禁忌

| 禁止 | 原因 |
|------|------|
| 使用 `<style>` 标签 | 微信会剥离所有 style 块 |
| `position: fixed/absolute` | 不支持 |
| `JavaScript` | 完全不支持 |
| `@font-face` 字体 | 不支持 |
| `display: flex/grid` | 部分设备不支持 |
| 超过 10MB 的图片 | 上传失败 |
| 非 HTTPS 图片 | 可能不显示 |

---

## 完整输出模板

```html
<section style="font-family:-apple-system,'PingFang SC','Helvetica Neue','Hiragino Sans GB',sans-serif;font-size:17px;line-height:1.9em;letter-spacing:0.02em;color:#1d1d1f;word-break:break-word;padding:0 16px;background:#ffffff;">

<!--正文内容 -->

<!-- 结尾署名区 -->
<div style="margin-top:4em;padding-top:2em;border-top:1px solid #d2d2d7;"><p style="margin:0;font-size:14px;color:#6e6e73;letter-spacing:0.03em;">结尾文字</p></div>

</section>
```
