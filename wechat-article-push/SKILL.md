---
name: wechat-article-push
description: |
  将已排版的微信公众号文章 HTML 推送到公众号草稿箱（零付费，微信原生 API）。
  当文章已完成排版、需要推送到公众号草稿箱时使用此技能。
  依赖 scripts/md2wechat-draft（已打包在 skill 内）。
  需要先配置 WeChat API 凭证（环境变量或 ~/.config/md2wechat/config.yaml）。
---

# 公众号文章推送

将带 inline style 的 HTML 文章通过微信原生 API 推送到公众号草稿箱，完全免费。

## 前置条件

### 配置 WeChat API 凭证

**方式一：环境变量（推荐）**

```bash
export WECHAT_APPID=你的AppID
export WECHAT_SECRET=你的AppSecret
```

**方式二：配置文件**

在 `~/.config/md2wechat/config.yaml` 中填入凭证：

```yaml
wechat:
  appid: 你的AppID
  secret: 你的AppSecret
```

获取方式：微信公众平台 → 设置与开发 → 基本配置 → AppID / AppSecret

## 工作流程

### Step 1：检查凭证

执行前检查 WeChat API 凭证是否已配置：

```bash
# 检查环境变量
echo "APPID: ${WECHAT_APPID:-未设置}"
echo "SECRET: ${WECHAT_SECRET:+已设置（隐藏）}"

# 或只检查配置文件是否存在，避免在终端输出密钥
test -f ~/.config/md2wechat/config.yaml \
  && echo "配置文件已存在" \
  || echo "配置文件不存在"
```

如果未配置，引导用户在本机设置环境变量，或自行将凭证写入
`~/.config/md2wechat/config.yaml`。不要要求用户在聊天消息中发送 AppSecret。

```bash
mkdir -p ~/.config/md2wechat
install -m 600 /dev/null ~/.config/md2wechat/config.yaml
cat > ~/.config/md2wechat/config.yaml << EOF
wechat:
  appid: ${WECHAT_APPID}
  secret: ${WECHAT_SECRET}
EOF
chmod 600 ~/.config/md2wechat/config.yaml
```

### Step 2：确认内容

确认文章 HTML 已完成排版、封面图已就位。

### Step 3：执行推送

凭证配置正确后，执行：

```bash
scripts/md2wechat-draft \
  --html "文章标题" "文章摘要（可选）" \
  /path/to/article.html \
  /path/to/cover.png
```

预期输出：

```
📡 获取 access_token...
✅ Token OK
🖼️ 上传封面...
✅ 封面: media_id
📝 读取 HTML...
✅ HTML 长度: xxx
🚀 推送草稿...
✅✅✅ 草稿推送成功！
```

### Step 4：存档封面图（可选）

封面图存档路径可自定义，例如：

```bash
mkdir -p ~/covers
cp /path/to/cover.png ~/covers/文章标题.png
```

## 常见问题

**Q：推送失败，提示"缺少 appid/secret"**
A：检查环境变量 `WECHAT_APPID` 和 `WECHAT_SECRET` 是否已设置，或 `~/.config/md2wechat/config.yaml` 是否存在且格式正确。

**Q：推送失败，提示 "invalid ip"（errcode 40164）**
A：当前机器的出口 IP 不在微信公众平台 IP 白名单中。去 微信公众平台 → 设置与开发 → 基本配置 → IP 白名单，添加报错信息中的 IP 地址。

**Q：推送失败，提示 "invalid appsecret"（errcode 40125）**
A：AppSecret 不正确或已过期。去 微信公众平台 → 设置与开发 → 基本配置 → AppSecret → 点击"重置"获取新的 Secret。

**Q：封面上传失败，能继续推草稿吗？**
A：可以。封面是可选的，推送命令去掉最后一个封面图参数即可。

**Q：md2wechat-draft 脚本在哪里？**
A：已打包在 skill 的 `scripts/md2wechat-draft` 下，安装后直接使用，无需额外安装。

**Q：为什么不用 md2wechat.cn 付费 API？**
A：本 skill 使用微信原生 API，不依赖任何第三方服务，完全免费。

## 与其他 skill 的配合

本 skill 是公众号文章生产流水线的最后一环：

```
公众号文章写作 → 公众号文章排版 → 公众号文章推送
```

- 写作 skill：输出 Markdown 纯文本
- 排版 skill：输出带 inline style 的 HTML
- 推送 skill：执行 md2wechat-draft 推草稿箱
