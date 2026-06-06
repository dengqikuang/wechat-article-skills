# WeChat Article Skills

一套用于微信公众号文章写作、排版和推送的 Codex/Agent skills。

## 包含内容

- `wechat-article-writing`：按公众号阅读习惯生成中文 Markdown 初稿。
- `wechat-article-format`：将 Markdown 转换为适合公众号的 inline-style HTML，内置 5 套主题。
- `wechat-article-push`：通过微信公众平台原生 API 将 HTML 推送到草稿箱。

## 安装

将需要的 skill 目录复制到你的 skills 目录，例如：

```bash
git clone https://github.com/dengqikuang/wechat-article-skills.git
cp -R wechat-article-skills/wechat-article-* ~/.agents/skills/
```

不同 Agent 的 skills 目录可能不同，请以对应产品的文档为准。

## 使用流程

```text
文章写作 -> 文章排版 -> 推送到公众号草稿箱
```

排版支持以下主题：

- `default`：字节范
- `github-readme`：GitHub 风格
- `editorial`：编辑风格
- `nyt-classic`：纽约时报范
- `apple`：苹果范

## 推送配置

推荐通过环境变量配置微信公众平台凭证：

```bash
export WECHAT_APPID="你的 AppID"
export WECHAT_SECRET="你的 AppSecret"
```

也可创建 `~/.config/md2wechat/config.yaml`：

```yaml
wechat:
  appid: 你的 AppID
  secret: 你的 AppSecret
```

请勿将真实凭证提交到 Git 仓库，也不要在聊天消息中发送 AppSecret。

推送脚本需要 Node.js。仅在直接转换 Markdown 时需要全局安装 `marked`：

```bash
npm install -g marked
```

## 隐私与网络请求

- 写作和排版 skill 在本地工作，不调用付费 API。
- 推送脚本只读取用户指定的文章、封面和本机微信凭证。
- 推送脚本只请求微信公众平台官方接口 `api.weixin.qq.com`。
- 仓库不包含任何真实 AppID、AppSecret 或个人文件路径。

## License

[MIT](LICENSE)
