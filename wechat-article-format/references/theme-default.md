# 字节范主题（bytedance）样式规则

> 适合场景：产品发布、功能介绍，科技评测、运营活动、重要公告
> 风格：强对比、现代感、科技质感、重点突出
> 调性参考：字节跳动产品官博、少数派产品测评、36氪报道

---

## 设计语言

| 属性 | 值 |
|------|------|
| 主色调 | `#fe2c55`（字节红，用于强调、h2 装饰） |
| 辅助色 | `#161823`（字节深黑，标题主色） |
| 正文颜色 | `#1a1a1a` |
| 次要文字 | `#888888` |
| 背景色 | `#ffffff` |
| 浅色背景 | `#f7f7f8`（列表、表格斑马纹） |
| 正文字号 | `15px` |
| 行高 | `1.8em` |
| 字间距 | `0.03em` |
| 字体 | `-apple-system, "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", sans-serif` |

---

## 元素级样式规则

---

### 容器（wrapper）

```html
<section style="
  font-family: -apple-system, 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
  font-size: 15px;
  line-height: 1.8em;
  letter-spacing: 0.03em;
  color: #1a1a1a;
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
  margin: 1.4em 0;
  font-size: 15px;
  line-height: 1.8em;
  color: #1a1a1a;
">段落内容</p>
```

---

### 二级标题（h2）

字节范最有辨识度的元素：**左侧红线 + 深黑粗字**，现代感强：

```html
<h2 style="
  font-size: 18px;
  font-weight: 700;
  color: #161823;
  border-left: 4px solid #fe2c55;
  padding: 4px 12px;
  margin: 2em 0 1em;
  line-height: 1.4;
  letter-spacing: 0.02em;
">标题文字</h2>
```

---

### 三级标题（h3）

```html
<h3 style="
  font-size: 16px;
  font-weight: 600;
  color: #161823;
  margin: 1.8em 0 0.6em;
  line-height: 1.4;
  padding-left: 8px;
  border-left: 2px solid #fe2c55;
">小节标题</h3>
```

---

### 四级标题（h4）

```html
<h4 style="
  font-size: 15px;
  font-weight: 600;
  color: #1a1a1a;
  margin: 1.5em 0 0.5em;
">四级标题</h4>
```

---

### 加粗（strong / b）

字节范加粗**使用红色**，体现强调和视觉冲击：

```html
<strong style="
  font-weight: 700;
  color: #fe2c55;
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

### 引用块（blockquote）

字节范 blockquote：**红色左线 + 浅红背景**，警示感强：

```html
<blockquote style="
  border-left: 4px solid #fe2c55;
  background: #fff5f6;
  padding: 12px 16px;
  margin: 1.8em 0;
  border-radius: 0 6px 6px 0;
">
  <p style="
    margin: 0;
    font-size: 14px;
    line-height: 1.8em;
    color: #333333;
  ">引用内容</p>
</blockquote>
```

---

### 分节符（代替 `---`）

字节范分节符用**细线 + 小红点**，保持科技感：

```html
<div style="
  display: flex;
  align-items: center;
  margin: 2.5em 0;
">
  <div style="flex: 1; height: 1px; background: #eeeeee;"></div>
  <div style="
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: #fe2c55;
    margin: 0 12px;
    flex-shrink: 0;
  "></div>
  <div style="flex: 1; height: 1px; background: #eeeeee;"></div>
</div>
```

---

### 无序列表（ul / li）

```html
<ul style="
  padding-left: 0;
  margin: 1.2em 0;
  list-style-type: none;
">
  <li style="
    margin: 0.6em 0;
    font-size: 15px;
    line-height: 1.8em;
    color: #1a1a1a;
    padding-left: 1.2em;
    position: relative;
  ">
    <span style="
      position: absolute;
      left: 0;
      top: 0.1em;
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background: #fe2c55;
      margin-top: 0.55em;
      display: inline-block;
    "></span>
    列表项内容
  </li>
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
    font-size: 15px;
    line-height: 1.8em;
    color: #1a1a1a;
  ">步骤内容</li>
</ol>
```

---

### 行内代码（code）

```html
<code style="
  font-family: 'Courier New', Consolas, monospace;
  font-size: 13px;
  color: #fe2c55;
  background: #fff5f6;
  padding: 2px 6px;
  border-radius: 4px;
">代码内容</code>
```

---

### 代码块（pre + code）

字节范代码块：**深色背景**，科技感十足：

```html
<pre style="
  background: #161823;
  border-radius: 8px;
  padding: 16px;
  margin: 1.5em 0;
  overflow-x: auto;
  font-size: 13px;
  line-height: 1.6;
"><code style="
  font-family: 'Courier New', Consolas, monospace;
  color: #e8e8e8;
  white-space: pre;
  word-break: normal;
">代码内容</code></pre>
```

---

### 标签/徽章（特色元素）

```html
<!-- 红色标签 -->
<span style="
  display: inline-block;
  font-size: 11px;
  font-weight: 600;
  color: #ffffff;
  background: #fe2c55;
  padding: 1px 7px;
  border-radius: 4px;
  letter-spacing: 0.05em;
  vertical-align: middle;
  margin-left: 6px;
">NEW</span>

<!-- 灰色标签 -->
<span style="
  display: inline-block;
  font-size: 11px;
  font-weight: 600;
  color: #ffffff;
  background: #888888;
  padding: 1px 7px;
  border-radius: 4px;
  letter-spacing: 0.05em;
  vertical-align: middle;
  margin-left: 6px;
">BETA</span>
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
        background: #161823;
        color: #ffffff;
        font-weight: 600;
        padding: 10px 12px;
        text-align: left;
      ">列头</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="
        padding: 9px 12px;
        border-bottom: 1px solid #eeeeee;
        background: #ffffff;
        color: #1a1a1a;
      ">内容</td>
    </tr>
    <tr>
      <td style="
        padding: 9px 12px;
        border-bottom: 1px solid #eeeeee;
        background: #f7f7f8;
        color: #1a1a1a;
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
  margin: 1.8em 0;
">
  <img src="图片URL" alt="图片描述" style="
    max-width: 100%;
    border-radius: 8px;
    display: block;
    margin: 0 auto;
  ">
  <figcaption style="
    font-size: 12px;
    color: #888888;
    margin-top: 6px;
  ">图片说明（可选）</figcaption>
</figure>
```

---

### 超链接（a）

```html
<span style="
  color: #fe2c55;
  border-bottom: 1px solid #fe2c55;
">链接文字</span>
<sup style="font-size: 10px; color: #888;">[1]</sup>
```

---

### 结尾署名区

```html
<div style="
  margin-top: 3em;
  padding: 16px;
  background: #f7f7f8;
  border-radius: 8px;
  border-left: 3px solid #fe2c55;
">
  <p style="
    margin: 0;
    font-size: 13px;
    color: #888888;
    line-height: 1.7;
  ">结尾文字 · 如有帮助欢迎转发</p>
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
| `display: grid` | 部分设备不支持 |
| 超过 10MB 的图片 | 上传失败 |
| 非 HTTPS 图片 | 可能不显示 |

---

## 完整输出模板

```html
<section style="font-family:-apple-system,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif;font-size:15px;line-height:1.8em;letter-spacing:0.03em;color:#1a1a1a;word-break:break-word;padding:0 10px;background:#ffffff;">

<!-- 正文内容 -->

<!-- 结尾 -->
<div style="margin-top:3em;padding:16px;background:#f7f7f8;border-radius:8px;border-left:3px solid #fe2c55;"><p style="margin:0;font-size:13px;color:#888888;line-height:1.7;">结尾文字</p></div>

</section>
```
