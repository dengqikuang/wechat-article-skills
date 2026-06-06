# GitHub 风格主题（github-readme）样式规则

> 适合场景：技术教程、开发工具介绍、产品文档、知识分享
> 风格：功能优先、代码友好，信息密度均衡、清晰无装饰
> 调性参考：GitHub README、技术博客、开发者内容

---

## 设计语言

| 属性 | 值 |
|------|------|
| 主色调 | `#0969da`（GitHub 蓝） |
| 正文颜色 | `#1f2328` |
| 次要文字 | `#636e7b` |
| 背景色 | `#ffffff` |
| 边框 / 分割线 | `#d1d9e0` |
| 代码背景 | `#f6f8fa`（GitHub 浅灰） |
| 正文字号 | `15px` |
| 行高 | `1.7em` |
| 字间距 | `0.01em` |
| 字体 | `-apple-system, "PingFang SC", "Segoe UI", "Noto Sans", "Helvetica Neue", sans-serif` |

---

## 元素级样式规则

---

### 容器（wrapper）

```html
<section style="
  font-family: -apple-system, 'PingFang SC', 'Segoe UI', 'Noto Sans', 'Helvetica Neue', sans-serif;
  font-size: 15px;
  line-height: 1.7em;
  letter-spacing: 0.01em;
  color: #1f2328;
  word-break: break-word;
  padding: 0 10px;
  background: #ffffff;
">
  <!-- 文章内容 -->
</section>
```

---

### 段落（p）

```html
<p style="
  margin: 1.2em 0;
  font-size: 15px;
  line-height: 1.7em;
  color: #1f2328;
">段落内容</p>
```

**写作规则**：
- 每段 3–6 句，信息密度可以高
- 技术内容用短句，保证每句话有明确含义

---

### 二级标题（h2）

github 主题 h2 用**底部细线**，干净但有层次感：

```html
<h2 style="
  font-size: 20px;
  font-weight: 600;
  color: #1f2328;
  border-bottom: 1px solid #d1d9e0;
  padding-bottom: 8px;
  margin: 2em 0 1em;
  line-height: 1.4;
">标题文字</h2>
```

**MD 写法规则**：
- `## 标题`，技术类标题可以更长（15 字以内）
- 前后各保留一个空行

---

### 三级标题（h3）

```html
<h3 style="
  font-size: 17px;
  font-weight: 600;
  color: #1f2328;
  margin: 1.8em 0 0.6em;
  line-height: 1.4;
">小节标题</h3>
```

---

### 四级标题（h4）

```html
<h4 style="
  font-size: 15px;
  font-weight: 600;
  color: #1f2328;
  margin: 1.5em 0 0.5em;
">四级标题</h4>
```

---

### 加粗（strong / b）

```html
<strong style="
  font-weight: 600;
  color: #1f2328;
">重要内容</strong>
```

---

### 斜体（em / i）

```html
<em style="
  font-style: italic;
  color: #1f2328;
">斜体内容</em>
```

---

### 引用块（blockquote）

github 主题引用块：**左侧浅灰线 + 灰色文字**，低调作为补充说明：

```html
<blockquote style="
  border-left: 4px solid #d1d9e0;
  padding: 4px 16px;
  margin: 1.5em 0;
  color: #636e7b;
">
  <p style="
    margin: 0;
    font-size: 15px;
    line-height: 1.7em;
  ">引用内容</p>
</blockquote>
```

**使用规则**：
- 适合：注意事项、补充说明、兼容性提示
- 不适合作为金句展示（用 h2 或加粗代替）

---

### 分节符（代替 `---`）

```html
<hr style="
  border: none;
  border-top: 1px solid #d1d9e0;
  margin: 2em 0;
">
```

---

### 无序列表（ul / li）

```html
<ul style="
  padding-left: 2em;
  margin: 1em 0;
  list-style-type: disc;
">
  <li style="
    margin: 0.4em 0;
    font-size: 15px;
    line-height: 1.7em;
    color: #1f2328;
  ">列表项内容</li>
</ul>
```

---

### 有序列表（ol / li）

```html
<ol style="
  padding-left: 2em;
  margin: 1em 0;
  list-style-type: decimal;
">
  <li style="
    margin: 0.4em 0;
    font-size: 15px;
    line-height: 1.7em;
    color: #1f2328;
  ">步骤内容</li>
</ol>
```

---

### 行内代码（code）

github 主题行内代码最接近真实 GitHub 样式：

```html
<code style="
  font-family: 'SFMono-Regular', 'SF Mono', 'Cascadia Mono', 'Segoe UI Mono', 'Courier New', monospace;
  font-size: 13px;
  color: #1f2328;
  background: #eff1f3;
  padding: 2px 6px;
  border-radius: 6px;
  border: 1px solid #d1d9e0;
">代码内容</code>
```

---

### 代码块（pre + code）

github 主题代码块：**浅灰背景 + 上下完整边框**，真实还原 GitHub README 代码块：

```html
<pre style="
  background: #f6f8fa;
  border: 1px solid #d1d9e0;
  border-radius: 6px;
  padding: 16px;
  margin: 1.5em 0;
  overflow-x: auto;
  font-size: 13px;
  line-height: 1.6;
"><code style="
  font-family: 'SFMono-Regular', 'SF Mono', 'Cascadia Mono', 'Courier New', monospace;
  color: #1f2328;
  white-space: pre;
  word-break: normal;
  background: transparent;
">代码内容</code></pre>
```

---

### 表格（table）

```html
<table style="
  width: 100%;
  border-collapse: collapse;
  margin: 1.5em 0;
  font-size: 14px;
">
  <thead>
    <tr>
      <th style="
        background: #f6f8fa;
        color: #1f2328;
        font-weight: 600;
        padding: 9px 12px;
        text-align: left;
        border: 1px solid #d1d9e0;
      ">列头</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="
        padding: 8px 12px;
        border: 1px solid #d1d9e0;
        background: #ffffff;
        color: #1f2328;
      ">内容</td>
    </tr>
    <tr>
      <td style="
        padding: 8px 12px;
        border: 1px solid #d1d9e0;
        background: #f6f8fa;
        color: #1f2328;
      ">内容（斑马条纹）</td>
    </tr>
  </tbody>
</table>
```

---

### 图片（img）

```html
<figure style="
  text-align: center;
  margin: 1.5em 0;
">
  <img src="图片URL" alt="图片描述" style="
    max-width: 100%;
    border-radius: 6px;
    border: 1px solid #d1d9e0;
    display: block;
    margin: 0 auto;
  ">
  <figcaption style="
    font-size: 12px;
    color: #636e7b;
    margin-top: 6px;
  ">图片说明（可选）</figcaption>
</figure>
```

---

### 超链接（a）

```html
<span style="
  color: #0969da;
  text-decoration: underline;
">链接文字</span>
<sup style="font-size: 10px; color: #636e7b;">[1]</sup>
```

---

### 提示框（Tip / Warning / Note）

github 主题特有元素，对应 GitHub Flavored Markdown 的 `> [!NOTE]` 语法：

```html
<!-- Note -->
<div style="
  border: 1px solid #0969da;
  border-radius: 6px;
  padding: 12px 16px;
  margin: 1.5em 0;
  background: #ddf4ff;
">
  <p style="
    margin: 0 0 4px;
    font-size: 13px;
    font-weight: 600;
    color: #0969da;
  ">📘 Note</p>
  <p style="margin: 0; font-size: 14px; color: #1f2328; line-height: 1.6;">提示内容</p>
</div>

<!-- Warning -->
<div style="
  border: 1px solid #bf8700;
  border-radius: 6px;
  padding: 12px 16px;
  margin: 1.5em 0;
  background: #fff8c5;
">
  <p style="
    margin: 0 0 4px;
    font-size: 13px;
    font-weight: 600;
    color: #bf8700;
  ">⚠️ Warning</p>
  <p style="margin: 0; font-size: 14px; color: #1f2328; line-height: 1.6;">警告内容</p>
</div>

<!-- Danger -->
<div style="
  border: 1px solid #cf222e;
  border-radius: 6px;
  padding: 12px 16px;
  margin: 1.5em 0;
  background: #ffebe9;
">
  <p style="
    margin: 0 0 4px;
    font-size: 13px;
    font-weight: 600;
    color: #cf222e;
  ">🚫 Important</p>
  <p style="margin: 0; font-size: 14px; color: #1f2328; line-height: 1.6;">重要提示内容</p>
</div>
```

**MD 写法规则**：
- 原 `> **注意：** 内容` 可替换为对应提示框
- 根据重要程度选 Note / Warning / Important

---

### 结尾署名区

```html
<div style="
  margin-top: 2.5em;
  padding-top: 1.5em;
  border-top: 1px solid #d1d9e0;
">
  <p style="
    margin: 0;
    font-size: 13px;
    color: #636e7b;
  ">结尾文字 · 版权归作者所有</p>
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
<section style="font-family:-apple-system,'PingFang SC','Segoe UI','Noto Sans','Helvetica Neue',sans-serif;font-size:15px;line-height:1.7em;letter-spacing:0.01em;color:#1f2328;word-break:break-word;padding:0 10px;background:#ffffff;">

<!-- 正文内容 -->

<!-- 结尾 -->
<div style="margin-top:2.5em;padding-top:1.5em;border-top:1px solid #d1d9e0;"><p style="margin:0;font-size:13px;color:#636e7b;">结尾文字</p></div>

</section>
```
