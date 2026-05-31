# 如何在Claude Code中使用Uns-Link key

OpenCode 是一个开源代理，帮助您使用任意 AI 模型编写和运行代码。它提供终端界面、桌面应用及 IDE 扩展。

官网：[Claude Code](https://claude.com/)

## 下载地址

- [macOS 下载](https://claude.ai/api/desktop/darwin/universal/dmg/latest/redirect)
- [Windows 下载](https://claude.ai/api/desktop/win32/x64/setup/latest/redirect)
- 终端安装：`curl -fsSL https://claude.ai/install.sh | bash` 或 `curl -fsSL https://claude.ai/install.cmd -o install.cmd && install.cmd && del install.cmd`

## 使用说明

1.在令牌管理界面创建令牌后，复制apikey。
![alt text](../images/05.png)
2. 找到 Claude Code 的配置文件 `settings.json` 。
常见路径如下：
`~/.claude/settings.json`（macOS）
`用户名\.claude\settings.json`（Windows）
如果文件或文件夹不存在，请手动创建，然后粘贴下方代码，并将 `apikey` 替换为你自己的密钥。

```yaml
{
  "env": {
    "ANTHROPIC_BASE_URL": "https://unslink.cc",
    "ANTHROPIC_AUTH_TOKEN": "sk-xxx",
    "CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC": "1",
    "CLAUDE_CODE_ATTRIBUTION_HEADER": "0"
  }
}
```

