# 如何在Codex中使用Uns-Link key

OpenCode 是一个开源代理，帮助您使用任意 AI 模型编写和运行代码。它提供终端界面、桌面应用及 IDE 扩展。

官网：[OpenCode](https://opencode.ai/zh)



## 📦  一、 核心组件获取与部署

请通过微软官方渠道完成基础架构的部署，以确保运行环境的安全与稳定：

1. 🛒 **访问商城**：启动系统内置的 Microsoft Store（微软商城）。
2. 🔍 **检索应用**：在搜索栏键入 `codex` 并执行检索。
3. ⬇️ **下载安装**：定位官方应用并点击**获取/安装**。
4. ⚡ **初次唤醒**：安装完毕后首次启动程序。此时系统会在后台自动构建初始化的本地目录结构，**无需进行任何交互**，静待其完成即可。

---

## ⚙️ 二、 核心网关与鉴权配置

基础环境构建完成后，需对本地通信参数进行深度定制。

📁 **配置工作目录**：`C:\Users\<您的用户名>\.codex`

###  📝 1. 注入环境参数 (`config.toml`)
进入上述目录并打开 `config.toml` 文件。请**保留原有的底层配置**，将以下模型调度与通信参数精准复制，并**粘贴至文件最顶端**：

```toml
# 核心通信与模型调度参数
model_provider = "cooper"
model = "gpt-5.5"
model_reasoning_effort = "high"
disable_response_storage = true
preferred_auth_method = "apikey"

[model_providers.cooper]
name = "cooper"
base_url = "https://cooper-api.com/v1"
wire_api = "responses"
```
注意：如果使用CCSWITCH配置，地址后面要加v1
 ###  🔑2. 构建鉴权凭证 (`auth.json`)
在同一目录下，**新建**名为 `auth.json` 的文件，以完成 API 通信的鉴权认证。请将您的专属密钥填入其中：

```json
{
  "OPENAI_API_KEY": "在此处替换为您的专属 API 密钥"
}
```

---

 ## 🔄 三、 系统重载与初始化

配置文件的变更需要彻底重启应用层方可生效。

> ⚠️ **运维须知**
> * 🛑 **彻底终止进程**：请勿仅关闭主窗口。务必在 Windows 右下角**系统托盘**中，右键单击 Codex 驻留图标并选择**退出**，以彻底释放后台进程。
> * ⏳ **冷启动加载**：重新唤醒 Codex 后，系统将进行环境重载与通信握手。该初始化过程通常会持续 **30 至 40 秒**，期间请耐心等待加载界面完成。