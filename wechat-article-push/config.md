# 公众号推送配置

_首次使用前请填写以下配置项。凭证仅用于调用微信草稿箱接口，不会发送到任何第三方服务。_

---

## 微信公众平台 API 凭证

```
appid: 你在微信公众平台获取的 AppID
secret: 你在微信公众平台获取的 AppSecret
```

获取方式：微信公众平台 → 设置与开发 → 基本配置 → AppID / AppSecret

---

## 脚本路径

`scripts/md2wechat-draft` — 已打包在 skill 内部，无需额外安装。

---

## 使用方式

配置文件放在 `~/.config/md2wechat/config.yaml`，格式如下：

```yaml
wechat:
  appid: 你的AppID
  secret: 你的AppSecret
```

或者通过环境变量传入：

```bash
export WECHAT_APPID=你的AppID
export WECHAT_SECRET=你的AppSecret
```

环境变量优先级高于配置文件。
