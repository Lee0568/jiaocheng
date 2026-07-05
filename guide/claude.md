# 如何在Claude Code中使用Uns-Link key

Claude Code 是一个开源代理，帮助您使用任意 AI 模型编写和运行代码。它提供终端界面、桌面应用及 IDE 扩展。

官网：[Claude Code](https://claude.com/)
cc-switch下载地址：[github]([https://openclaw.ai/](https://github.com/farion1231/cc-switch/releases/download/v3.16.1/CC-Switch-v3.16.1-Windows-Portable.zip))

## 下载地址

- [macOS 下载](https://claude.ai/api/desktop/darwin/universal/dmg/latest/redirect)
- [Windows 下载](https://claude.ai/api/desktop/win32/x64/setup/latest/redirect)
- 终端安装：`curl -fsSL https://claude.ai/install.sh | bash` 或 `curl -fsSL https://claude.ai/install.cmd -o install.cmd && install.cmd && del install.cmd`

## 使用说明

1.在令牌管理界面创建令牌后，复制apikey。

<img src="../images/05.png" alt="alt text" width="600" />

注意：如果要使用claude、gemini、grok，以及更快速的gpt模型需要切换成vip分组。同理需要使用低价模型可以切换分组为free分组，如果不切换默认使用default的分组，此分组只能使用部分性能较差的模型。

<img src="../images/33.png" alt="alt text" width="600" />

### 方法一：使用cc-switch

运行cc-switch，选择openclaw，点击添加供应商。

<img src="../images/28.png" alt="alt text" width="600" />

依次填入信息`https://unslink.cc/v1`

<img src="../images/29.png" alt="alt text" width="600" />
<img src="../images/30.png" alt="alt text" width="600" />

注意：需要使用claude模型需要将api协议调整为Anthropic Messages。

<img src="../images/34.png" alt="alt text" width="600" />

保存之后点击添加，即可开始在openclaw里对话。

<img src="../images/31.png" alt="alt text" width="600" />
<img src="../images/32.png" alt="alt text" width="600" />

注意：openclaw极其烧token，推荐使用便宜的模型，不要使用太贵的。

