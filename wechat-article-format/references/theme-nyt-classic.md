# NYT 经典主题（nyt-classic）样式规则

> 适合场景：深度报道、行业分析，知识长文、财经评论
> 风格：密集排版、强信息密度、编辑部质感
> 调性参考：《纽约时报》《经济学人》数字版正文

---

## 设计语言

| 属性 | 值 |
|------|------|
| 主色调 | `#121212`（深黑，标题主色） |
| 强调色 | `#c0392b`（编辑红，用于重点标注） |
| 正文颜色 | `#2b2b2b` |
| 次要文字 | `#767676` |
| 背景色 | `#f9f7f2`（米黄纸感背景） |
| 分割线色 | `#1a1a1a` |
| 正文字号 | `16px` |
| 行高 | `1.9em` |
| 字间距 | `0.02em`（收紧，体现报纸密度感） |
| 字体 | `Georgia, "Noto Serif SC", "Source Han Serif SC", "PingFang SC", serif` |

> **注意**：NYT 主题使用衬线字体堆叠，在 iOS 上会优先渲染 Georgia，安卓上回落 PingFang SC。正文用衬线是本主题与其他主题最核心的差异。

---

## 元素级样式规则

---

### 容器（wrapper）

```html
<section style="
  font-family: Georgia, 'Noto Serif SC', 'Source Han Serif SC', 'PingFang SC', serif;
  font-size: 16px;
  line-height: 1.9em;
  letter-spacing: 0.02em;
  color: #2b2b2b;
  word-break: break-word;
  padding: 0 10px;
  background: #f9f7f2;
">
  <!-- 文章内容 -->
</section>
```

---

### 顶部刊头装饰

NYT 主题在文章最顶部加一条粗黑线，模拟报纸版面感：

```html
<div style="
  border-top: 3px solid #121212;
  border-bottom: 1px solid #121212;
  padding: 6px 0;
  margin-bottom: 2em;
  text-align: center;
">
  <span style="
    font-size: 11px;
    letter-spacing: 0.2em;
    color: #767676;
    text-transform: uppercase;
  ">OPINION · ANALYSIS</span>
</div>
```

---

### 段落（p）

```html
<p style="
  margin: 1.4em 0;
  font-size: 16px;
  line-height: 1.9em;
  color: #2b2b2b;
  text-align: justify;
">段落内容</p>
```

---

### 二级标题（h2）

NYT 主题 h2 用**全大写字感 + 顶部细红线**，体现编辑分类感：

```html
<h2 style="
  font-size: 20px;
  font-weight: bold;
  color: #121212;
  border-top: 3px solid #c0392b;
  padding-top: 10px;
  margin: 2.5em 0 0.8em;
  line-height: 1.4;
  letter-spacing: 0.04em;
  font-family: Georgia, 'PingFang SC', serif;
">标题文字</h2>
```

---

### 三级标题（h3）

```html
<h3 style="
  font-size: 17px;
  font-weight: bold;
  color: #121212;
  margin: 2em 0 0.6em;
  line-height: 1.5;
  letter-spacing: 0.03em;
  font-family: Georgia, 'PingFang SC', serif;
">小节标题</h3>
```

---

### 四级标题（h4）

```html
<h4 style="
  font-size: 15px;
  font-weight: bold;
  color: #2b2b2b;
  margin: 1.5em 0 0.5em;
  letter-spacing: 0.05em;
  text-transform: uppercase;
">四级标题</h4>
```

---

### 加粗（strong / b）

NYT 主题加粗**使用编辑红色**，体现报纸重点标注习惯：

```html
<strong style="
  font-weight: bold;
  color: #c0392b;
">重要内容</strong>
```

---

### 斜体（em / i）

```html
<em style="
  font-style: italic;
  color: #2b2b2b;
  font-family: Georgia, serif;
">斜体内容</em>
```

---

### 引用块（blockquote）

NYT 主题引用块模拟**报纸大引言**风格：左侧粗线 + 字号放大 + 衬线字体：

```html
<blockquote style="
  border-left: 4px solid #121212;
  padding: 8px 20px;
  margin: 2em 0;
  background: transparent;
">
  <p style="
    margin: 0;
    font-size: 19px;
    line-height: 1.7em;
    color: #121212;
    font-style: italic;
    font-family: Georgia, 'Noto Serif SC', serif;
    letter-spacing: 0.02em;
  ">引用内容</p>
  <cite style="
    display: block;
    margin-top: 8px;
    font-size: 12px;
    color: #767676;
    font-style: normal;
    letter-spacing: 0.05em;
  ">— 来源或作者</cite>
</blockquote>
```

---

### 分节符（代替 `---`）

NYT 主题用**三条细线**分节，模拟报纸版块分割：

```html
<div style="
  text-align: center;
  margin: 2.5em 0;
">
  <span style="
    display: inline-block;
    width: 40px;
    height: 1px;
    background: #1a1a1a;
    vertical-align: middle;
  "></span>
  <span style="
    display: inline-block;
    width: 6px;
    height: 6px;
    background: #c0392b;
    border-radius: 50%;
    vertical-align: middle;
    margin: 0 8px;
  "></span>
  <span style="
    display: inline-block;
    width: 40px;
    height: 1px;
    background: #1a1a1a;
    vertical-align: middle;
  "></span>
</div>
```

---

### 无序列表（ul / li）

```html
<ul style="
  padding-left: 1.5em;
  margin: 1.2em 0;
  list-style-type: square;
">
  <li style="
    margin: 0.6em 0;
    font-size: 16px;
    line-height: 1.9em;
    color: #2b2b2b;
  ">列表项内容</li>
</ul>
```

---

### 有序列表（ol / li）

```html
<ol style="
  padding-left: 1.5em;
  margin: 1.2em 0;
  list-style-type: decimal;
">
  <li style="
    margin: 0.6em 0;
    font-size: 16px;
    line-height: 1.9em;
    color: #2b2b2b;
  ">步骤内容</li>
</ol>
```

---

### 行内代码（code）

```html
<code style="
  font-family: 'Courier New', Consolas, monospace;
  font-size: 14px;
  color: #c0392b;
  background: #fdf2f0;
  padding: 2px 5px;
  border-radius: 2px;
">代码内容</code>
```

---

### 代码块（pre + code）

```html
<pre style="
  background: #f0ede6;
  border-radius: 4px;
  padding: 16px;
  margin: 1.8em 0;
  overflow-x: auto;
  font-size: 13px;
  line-height: 1.7;
  border-left: 3px solid #c0392b;
"><code style="
  font-family: 'Courier New', Consolas, monospace;
  color: #2b2b2b;
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
  margin: 1.8em 0;
  font-size: 14px;
  font-family: Georgia, 'PingFang SC', serif;
">
  <thead>
    <tr>
      <th style="
        background: #121212;
        color: #f9f7f2;
        font-weight: bold;
        padding: 10px 12px;
        text-align: left;
        letter-spacing: 0.05em;
      ">列头</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="
        padding: 9px 12px;
        border-bottom: 1px solid #d8d4cc;
        background: #f9f7f2;
        color: #2b2b2b;
      ">内容</td>
    </tr>
    <tr>
      <td style="
        padding: 9px 12px;
        border-bottom: 1px solid #d8d4cc;
        background: #f0ede6;
        color: #2b2b2b;
      ">内容（斑马条纹）</td>
    </tr>
  </tbody>
</table>
```

---

### 分割线（hr）

```html
<hr style="
  border: none;
  border-top: 1px solid #1a1a1a;
  margin: 2.5em 0;
">
```

---

### 图片（img）

```html
<figure style="
  text-align: center;
  margin: 2em -10px;
">
  <img src="图片URL" alt="图片描述" style="
    max-width: 100%;
    display: block;
    margin: 0 auto;
  ">
  <figcaption style="
    font-size: 12px;
    color: #767676;
    margin-top: 6px;
    font-style: italic;
    font-family: Georgia, serif;
    letter-spacing: 0.03em;
  ">图片说明 / 摄影：来源</figcaption>
</figure>
```

---

### 超链接（a）

```html
<span style="
  color: #2b2b2b;
  border-bottom: 1px solid #c0392b;
">链接文字</span>
<sup style="font-size: 10px; color: #767676;">[1]</sup>
```

---

### 结尾署名区

```html
<div style="
  margin-top: 3em;
  padding: 1.5em 0;
  border-top: 3px solid #121212;
  border-bottom: 1px solid #121212;
">
  <p style="
    margin: 0;
    font-size: 12px;
    color: #767676;
    letter-spacing: 0.1em;
    font-family: Georgia, serif;
    font-style: italic;
  ">结尾文字 / 版权归作者所有</p>
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
<section style="font-family:Georgia,'Noto Serif SC','Source Han Serif SC','PingFang SC',serif;font-size:16px;line-height:1.9em;letter-spacing:0.02em;color:#2b2b2b;word-break:break-word;padding:0 10px;background:#f9f7f2;">

<!-- 刊头装饰 -->
<div style="border-top:3px solid #121212;border-bottom:1px solid #121212;padding:6px 0;margin-bottom:2em;text-align:center;"><span style="font-size:11px;letter-spacing:0.2em;color:#767676;">OPINION · ANALYSIS</span></div>

<!--正文内容 -->

<!-- 结尾署名区 -->
<div style="margin-top:3em;padding:1.5em 0;border-top:3px solid #121212;border-bottom:1px solid #121212;"><p style="margin:0;font-size:12px;color:#767676;letter-spacing:0.1em;font-family:Georgia,serif;font-style:italic;">结尾文字</p></div>

</section>
```
