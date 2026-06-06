# WeChat Article Skills

> 把一个选题，变成一篇能读、好看、可以直接进入微信公众号草稿箱的文章。

写公众号最消耗人的，往往不是“写出一句话”，而是后面一连串琐碎工作：

- AI 写出来的内容太像说明书，还要反复调整语气
- Markdown 到公众号后台后，标题、引用、代码块全乱了
- 每篇文章都要重新挑颜色、调间距、处理样式
- 排版完成后，还要上传封面、复制正文、填写摘要
- 写作、排版、发布分散在不同工具里，流程很难复用

**WeChat Article Skills** 把这些步骤拆成 3 个可以独立使用、也可以串联工作的 Agent Skill：

```text
一个选题
   ↓
写成适合公众号阅读的中文文章
   ↓
套用一套稳定、统一的视觉主题
   ↓
通过微信官方 API 进入草稿箱
```

它不是又一个在线编辑器，而是一套可以交给 Agent 重复执行的公众号内容工作流。

## 它能带来什么

### 1. 让文章更像“人写的”

`wechat-article-writing` 不只负责扩写文字，还定义了一套公众号写作规则：

- 开头直接给结论，不用长篇铺垫
- 使用短句和短段落，适合手机阅读
- 保留口语感，同时控制信息密度
- 优先使用具体工具、场景和数据
- 自动生成多个兼顾点击率与搜索的标题
- 检查第一人称视角，避免 AI 把自己写进文章
- 针对微信传播环境检查敏感表达

它的目标不是生成一篇“正确但无聊”的文章，而是帮你形成稳定、可复用的个人表达方式。

### 2. 不再手工折腾公众号排版

`wechat-article-format` 会把 Markdown 转换为带 inline style 的 HTML，并针对公众号编辑器做结构优化：

- 自动规范标题层级
- 拆分过长段落
- 处理外链、图片、表格和引用
- 替换公众号不兼容的 Markdown 语法
- 所有样式内联，不依赖外部 CSS

内置 5 套主题：

| 主题 | 风格 | 适合内容 |
| --- | --- | --- |
| `default` | 字节范，红黑高对比 | 产品发布、科技评测、知识分享 |
| `github-readme` | 清晰、克制、代码友好 | 技术教程、开发工具、产品文档 |
| `editorial` | 暖色、留白、杂志感 | 品牌故事、个人专栏、人文内容 |
| `nyt-classic` | 衬线字体、报刊质感 | 行业分析、财经评论、深度长文 |
| `apple` | 极简、大字号、大留白 | 产品介绍、设计内容、精品文章 |

你可以把同一篇 Markdown 快速切换成不同视觉风格，不需要每次重新设计。

### 3. 从 HTML 直接进入公众号草稿箱

`wechat-article-push` 使用微信公众平台原生 API：

- 上传封面图
- 读取已经排版好的 HTML
- 填写标题和摘要
- 创建公众号草稿

不依赖第三方推送平台，也不需要购买排版 API。凭证保存在你的本机，推送请求只发送到微信官方接口。

## 适合谁

- 经常写技术教程、产品评测或知识分享的公众号作者
- 希望保持固定文字风格和视觉风格的个人创作者
- 同时维护多个栏目，需要减少重复操作的内容团队
- 正在用 Codex 或其他 Agent 搭建内容生产工作流的人
- 不想把公众号凭证交给第三方服务的开发者

## 三个 Skill 如何协作

### 写作

你可以给 Agent 一个选题、一段素材，或者一份粗略提纲：

```text
写一篇公众号文章，介绍我如何用 NAS 自动备份照片。
读者是刚接触自托管的普通用户，重点解释为什么值得做。
```

Agent 会先生成 Markdown 初稿和备选标题，等待你确认内容。

### 排版

内容确认后，选择适合文章的主题：

```text
用 GitHub 风格排版这篇文章。
```

Agent 会读取对应主题规则，输出可以用于公众号的 inline-style HTML。

### 推送

准备好封面图并配置微信凭证后：

```text
把排版后的文章推送到公众号草稿箱。
```

文章会进入草稿箱，最后的预览、检查和正式发布仍由你完成。

## 安装

克隆仓库：

```bash
git clone https://github.com/dengqikuang/wechat-article-skills.git
```

将 3 个目录复制到 Agent 的 skills 目录。以 `~/.agents/skills/` 为例：

```bash
cp -R wechat-article-skills/wechat-article-* ~/.agents/skills/
```

不同 Agent 的 skills 目录可能不同，请以对应产品的文档为准。

仓库结构：

```text
wechat-article-skills/
├── wechat-article-writing/
│   └── SKILL.md
├── wechat-article-format/
│   ├── SKILL.md
│   └── references/
└── wechat-article-push/
    ├── SKILL.md
    ├── config.md
    └── scripts/
```

## 配置公众号推送

推送功能需要微信公众号的 `AppID` 和 `AppSecret`。

推荐使用环境变量：

```bash
export WECHAT_APPID="你的 AppID"
export WECHAT_SECRET="你的 AppSecret"
```

也可以创建 `~/.config/md2wechat/config.yaml`：

```yaml
wechat:
  appid: 你的 AppID
  secret: 你的 AppSecret
```

建议限制配置文件权限：

```bash
chmod 600 ~/.config/md2wechat/config.yaml
```

推送脚本需要 Node.js。只有在脚本直接转换 Markdown 时，才需要全局安装 `marked`：

```bash
npm install -g marked
```

## 隐私与安全

- 仓库不包含真实的 `AppID`、`AppSecret` 或个人文件路径
- 写作和排版规则不会主动读取你的微信凭证
- 推送脚本只读取指定的文章、封面图和本机凭证
- 推送脚本只请求微信公众平台官方接口 `api.weixin.qq.com`
- 请勿把真实凭证提交到 Git，也不要在聊天消息中发送 `AppSecret`

## 能力边界

- 写作质量取决于使用的 Agent、模型和输入素材
- “不依赖付费 API”指排版与微信推送流程本身，不代表所使用的 AI 模型一定免费
- 微信后台可能调整 HTML 兼容规则，正式发布前应在草稿箱中预览
- 这套 Skill 帮你减少机械工作，但选题判断、事实核查和最终发布仍需要作者负责

## License

[MIT](LICENSE)
