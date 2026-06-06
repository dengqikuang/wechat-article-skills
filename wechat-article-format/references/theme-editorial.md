# 编辑风格主题（editorial）样式规则

> 适合场景：深度文章，品牌故事、个人专栏、散文随笔、人文观察
> 风格：大行距、暖色调、克制装饰、留白充足
> 调性参考：人文类杂志正文、纸质书排版

---

## 设计语言

| 属性 | 值 |
|------|------|
| 主色调 | `#c8b89a`（暖金，用于装饰线、分节符） |
| 正文颜色 | `#1a1a1a`（近黑，比纯黑更温润） |
| 次要文字 | `#999999`（署名、注释、图注） |
| 背景色 | `#fafaf8`（米白，有纸感） |
| 分割线色 | `#e0d8cc`（暖灰） |
| 正文字号 | `16px` |
| 行高 | `2em` |
| 字间距 | `0.06em` |
| 字体 | `-apple-system, "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", sans-serif` |

---

## 元素级样式规则

---

### 容器（wrapper）

```html
<section style="
  font-family: -apple-system, 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
  font-size: 16px;
  line-height: 2em;
  letter-spacing: 0.06em;
  color: #1a1a1a;
  word-break: break-word;
  padding: 0 12px;
  background: #fafaf8;
">
  <!-- 文章内容 -->
</section>
```

---

### 题图装饰（文章最顶部，固定使用一次）

```html
<div style="
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 40px;
">
  <div style="height: 1px; width: 40px; background: #c8b89a;"></div>
  <div style="width: 5px; height: 5px; border-radius: 50%; background: #c8b89a; margin: 0 10px;"></div>
  <div style="height: 1px; width: 40px; background: #c8b89a;"></div>
</div>
```

---

### 段落（p）

```html
<p style="
  margin: 1.8em 0;
  font-size: 16px;
  line-height: 2em;
  color: #1a1a1a;
">段落内容</p>
```

---

### 二级标题（h2）

editorial 主题不用色块，改为**居中无装饰**，让文字本身承重：

```html
<h2 style="
  font-size: 18px;
  font-weight: bold;
  color: #1a1a1a;
  text-align: center;
  margin: 2.5em 0 1.2em;
  letter-spacing: 0.1em;
  line-height: 1.5;
">标题文字</h2>
```

---

### 三级标题（h3）

```html
<h3 style="
  font-size: 16px;
  font-weight: bold;
  color: #1a1a1a;
  margin: 2em 0 0.8em;
  letter-spacing: 0.06em;
  line-height: 1.6;
">小节标题</h3>
```

---

### 四级标题（h4）

```html
<h4 style="
  font-size: 15px;
  font-weight: bold;
  color: #555555;
  margin: 1.5em 0 0.6em;
  letter-spacing: 0.05em;
">四级标题</h4>
```

---

### 加粗（strong / b）

editorial 主题加粗**保持正文颜色，不引入强调色**：

```html
<strong style="
  font-weight: bold;
  color: #1a1a1a;
">重要内容</strong>
```

---

### 斜体（em / i）

```html
<em style="
  font-style: italic;
  color: #555555;
">斜体内容</em>
```

---

### 引用块 / 金句块（blockquote）

editorial 最有特色的元素：**上下细线夹住、居中大字**，提炼全文核心句。

```html
<blockquote style="
  margin: 2.5em 8px;
  padding: 20px 0;
  border-top: 1px solid #e0d8cc;
  border-bottom: 1px solid #e0d8cc;
  text-align: center;
">
  <p style="
    margin: 0;
    font-size: 17px;
    line-height: 1.8em;
    color: #1a1a1a;
    font-weight: bold;
    letter-spacing: 0.08em;
  ">金句内容</p>
</blockquote>
```

---

### 分节符（代替 `---`）

editorial 主题用**居中点阵**替代横线，更轻盈：

```html
<div style="
  text-align: center;
  margin: 2.5em 0;
  color: #c8b89a;
  letter-spacing: 8px;
  font-size: 14px;
">· · ·</div>
```

---

### 无序列表（ul / li）

```html
<ul style="
  padding-left: 1.5em;
  margin: 1.2em 0;
  list-style-type: disc;
">
  <li style="
    margin: 0.8em 0;
    font-size: 16px;
    line-height: 2em;
    color: #1a1a1a;
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
    margin: 0.8em 0;
    font-size: 16px;
    line-height: 2em;
    color: #1a1a1a;
  ">步骤内容</li>
</ol>
```

---

### 行内代码（code）

```html
<code style="
  font-family: 'Courier New', Consolas, monospace;
  font-size: 14px;
  color: #555555;
  background: #f0ece4;
  padding: 2px 6px;
  border-radius: 3px;
">代码内容</code>
```

---

### 代码块（pre + code）

editorial 主题代码块用**暖色浅背景**，保持整体调性一致：

```html
<pre style="
  background: #f5f0e8;
  border-radius: 6px;
  padding: 16px;
  margin: 1.8em 0;
  overflow-x: auto;
  font-size: 13px;
  line-height: 1.7;
  border-left: 3px solid #c8b89a;
"><code style="
  font-family: 'Courier New', Consolas, monospace;
  color: #333333;
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
">
  <thead>
    <tr>
      <th style="
        background: #f0ece4;
        color: #1a1a1a;
        font-weight: bold;
        padding: 10px 12px;
        text-align: left;
        border-bottom: 2px solid #c8b89a;
      ">列头</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="
        padding: 10px 12px;
        border-bottom: 1px solid #e0d8cc;
        background: #fafaf8;
        color: #1a1a1a;
      ">内容</td>
    </tr>
    <tr>
      <td style="
        padding: 10px 12px;
        border-bottom: 1px solid #e0d8cc;
        background: #f5f0e8;
        color: #1a1a1a;
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
  border-top: 1px solid #e0d8cc;
  margin: 2.5em 0;
">
```

---

### 图片（img）

```html
<figure style="
  text-align: center;
  margin: 2em 0;
">
  <img src="图片URL" alt="图片描述" style="
    max-width: 100%;
    border-radius: 4px;
    display: block;
    margin: 0 auto;
  ">
  <figcaption style="
    font-size: 12px;
    color: #999999;
    margin-top: 8px;
    letter-spacing: 0.05em;
  ">图片说明（可选）</figcaption>
</figure>
```

---

### 超链接（a）

```html
<span style="color: #c8b89a; border-bottom: 1px solid #c8b89a;">链接文字</span>
<sup style="font-size: 10px; color: #999;">[1]</sup>
```

---

### 结尾署名区（每篇固定结尾）

```html
<div style="
  margin-top: 3.5em;
  padding-top: 2em;
  border-top: 1px solid #e0d8cc;
  text-align: center;
">
  <p style="
    margin: 0 0 0.8em;
    font-size: 13px;
    color: #999999;
    letter-spacing: 0.1em;
  ">结尾文字（公众号名 / slogan / 引导关注语）</p>
  <div style="
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 1em;
  ">
    <div style="height: 1px; width: 30px; background: #c8b89a;"></div>
    <div style="width: 4px; height: 4px; border-radius: 50%; background: #c8b89a; margin: 0 8px;"></div>
    <div style="height: 1px; width: 30px; background: #c8b89a;"></div>
  </div>
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
| `display: flex/grid` | 部分设备不支持（仅限正文区域） |
| 超过 10MB 的图片 | 上传失败 |
| 非 HTTPS 图片 | 可能不显示 |

---

## 完整输出模板

```html
<section style="font-family:-apple-system,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif;font-size:16px;line-height:2em;letter-spacing:0.06em;color:#1a1a1a;word-break:break-word;padding:0 12px;background:#fafaf8;">

<!-- 题图装饰 -->
<div style="display:flex;align-items:center;justify-content:center;margin-bottom:40px;"><div style="height:1px;width:40px;background:#c8b89a;"></div><div style="width:5px;height:5px;border-radius:50%;background:#c8b89a;margin:0 10px;"></div><div style="height:1px;width:40px;background:#c8b89a;"></div></div>

<!--正文内容 -->

<!-- 结尾署名区 -->
<div style="margin-top:3.5em;padding-top:2em;border-top:1px solid #e0d8cc;text-align:center;"><p style="margin:0 0 0.8em;font-size:13px;color:#999999;letter-spacing:0.1em;">结尾文字</p><div style="display:flex;align-items:center;justify-content:center;margin-top:1em;"><div style="height:1px;width:30px;background:#c8b89a;"></div><div style="width:4px;height:4px;border-radius:50%;background:#c8b89a;margin:0 8px;"></div><div style="height:1px;width:30px;background:#c8b89a;"></div></div></div>

</section>
```
