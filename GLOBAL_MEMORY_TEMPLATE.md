# 📋 DingTalk 配置模板

> ⚠️ **重要：** 请勿上传真实的 API Key、Secret、Token 到公开仓库！
> 
> 此文件仅作为配置参考模板，请务必替换为您的实际配置。

## 钉钉应用配置

```markdown
# DingTalk Configuration Template (Example Only!)

## Required Fields

### App Key / Client ID
dingdadyh0gozaxaahyx
*(格式: 字母+数字组合，用于身份认证)*

### App Secret
hPAAgcT6izWXYfxSfjuOawZ8xMXYpfSjtxhTD02eF24vDh5CQBgNk3hN4Q0XK8DQ
*(格式: 40位字符串，用于获取access_token，请妥善保管！)*

### Robot Code
dingdadyh0gozaxaahyx
*(通常与AppKey相同，用于机器人身份标识)*

### Corp ID (企业ID)
ding21ae2bf232bad777ee0f45d8e4f7c288
*(格式: ding开头的企业唯一标识)*

### Agent ID (应用ID)
4257890665
*(数字格式，钉钉应用的唯一标识)*

### unionId
fQwM0KWXFefVDW5SyOG8VwiEiE
*(用户统一ID，用于知识库等API调用)*

## 获取方式

1. **登录钉钉开放平台**: https://open-dev.dingtalk.com/
2. **创建企业内部应用**
3. **获取凭证信息**:
   - AppKey / AppSecret: "凭证管理"页面
   - Corp ID: "基本信息"页面
   - Agent ID: "应用信息"页面
4. **配置权限**: 根据需要开启相应API权限

## 安全建议

✅ **正确做法:**
- ✅ 将敏感信息存储在本地配置文件
- ✅ 使用环境变量管理密钥
- ✅ 定期更换 App Secret
- ✅ 设置 IP 白名单限制访问

❌ **错误做法:**
- ❌ 上传真实凭证到公开仓库
- ❌ 在代码中硬编码密钥
- ❌ 通过聊天工具发送敏感信息
- ❌ 分享凭证给他人

## OpenClaw 配置示例

在 `~/.openclaw/openclaw.json` 中：

```json
{
  "channels": {
    "dingtalk": {
      "enabled": true,
      "clientId": "你的AppKey",
      "clientSecret": "你的AppSecret",
      "robotCode": "你的RobotCode",
      "corpId": "你的CorpID",
      "agentId": "你的AgentID",
      "dmPolicy": "open",
      "groupPolicy": "open",
      "messageType": "markdown"
    }
  }
}
```

## 敏感信息清单

以下信息**必须脱敏**后上传：

| 信息类型 | 是否需要脱敏 | 示例 |
|---------|------------|-----|
| AppKey | ✅ 是 | `dingdadyh0gozaxaahyx` → `YOUR_APP_KEY` |
| AppSecret | ✅ 是 | `hPAAgcT6izWXY...` → `YOUR_APP_SECRET` |
| Robot Code | ✅ 是 | `dingdadyh0gozaxaahyx` → `YOUR_ROBOT_CODE` |
| Corp ID | ✅ 是 | `ding21ae2bf232...` → `YOUR_CORP_ID` |
| Agent ID | ✅ 是 | `4257890665` → `YOUR_AGENT_ID` |
| unionId | ✅ 是 | `fQwM0KWXFefV...` → `YOUR_UNION_ID` |
| Access Token | ✅ 是 | 临时令牌，**绝对不能上传** |

以下信息**可以公开**（如已广泛使用）：

| 信息类型 | 是否可公开 | 示例 |
|---------|----------|-----|
| Corp ID | ⚠️ 视情况 | 企业公开标识，可公开 |
| App ID | ⚠️ 视情况 | 应用标识，可公开 |

## ⚠️ 重要提醒

1. **永远不要**将 App Secret 上传到任何公开仓库
2. **定期检查**已上传的文件，确保无敏感信息泄露
3. **如果泄露**，立即到钉钉开放平台重置 App Secret
4. **使用 .gitignore** 忽略包含敏感信息的本地文件
