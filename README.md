<a href="https://trendshift.io/repositories/1692" target="_blank"><img src="https://trendshift.io/api/badge/repositories/1692" alt="xtekky%2Fgpt4free | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>

---

<p align="center">
  <span style="background: linear-gradient(45deg, #12c2e9, #c471ed, #f64f59); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">
    <strong>作者 <a href="https://github.com/xtekky">@xtekky</a></strong>
  </span>
</p>

<div id="top"></div>

> [!重要提示]
> 使用本存储库或任何相关代码，即表示您同意[法律声明](LEGAL_NOTICE.md)。本仓库的作者**不对使用承担责任，也不认可**该仓库，也不对任何副本、分支、其他用户重新上传或任何其他与GPT4Free相关的内容负责。这是作者的唯一账号和存储库。为防止冒充或不负责任的行为，请遵守本存储库使用的GNU GPL许可证。

> [!警告]
> _"gpt4free"_ 是一个**概念验证(PoC)**，展示了具有多提供商请求功能的API包的开发，包括超时、负载均衡和流量控制等功能。

> [!注意]
> <sup><strong>最新版本:</strong></sup><br> [![PyPI version](https://img.shields.io/pypi/v/g4f?color=blue)](https://pypi.org/project/g4f) [![Docker version](https://img.shields.io/docker/v/hlohaus789/g4f?label=docker&color=blue)](https://hub.docker.com/r/hlohaus789/g4f)  
> <sup><strong>统计数据:</strong></sup><br> [![Downloads](https://static.pepy.tech/badge/g4f)](https://pepy.tech/project/g4f) [![Downloads](https://static.pepy.tech/badge/g4f/month)](https://pepy.tech/project/g4f)

```sh
pip install -U g4f[all]
```

```sh
docker pull hlohaus789/g4f
```

## 🆕 最新动态

![1000032415](https://github.com/user-attachments/assets/4caab977-eb05-48ed-b750-3ad082bcfcae)

- **探索最新功能和更新**  
  在[发布页面](https://github.com/xtekky/gpt4free/releases)查看全面详情。  

- **关注我们的Telegram频道** 📨  
  加入[telegram.me/g4f_channel](https://telegram.me/g4f_channel)。
  
- **订阅Discord新闻频道** 💬🆕️  
  通过[Discord新闻频道: discord.gg/5E39JUWUFa](https://discord.gg/5E39JUWUFa)了解更新。
  
- **在Discord社区获取支持** 🤝💻  
  通过[支持群组: discord.gg/qXA4Wf4Fsm](https://discord.gg/qXA4Wf4Fsm)获取帮助。

## 🔻 网站下线

如果您的站点在本仓库中且您想将其下线，请发送电子邮件至takedown@g4f.ai并提供证明其属于您的证据，我们将尽快移除。为防止重新出现，请保护您的API。😉

## 🚀 GPT4Free on HuggingFace
[![HuggingSpace](https://github.com/user-attachments/assets/1d859e8a-d6fa-416f-a213-ccc26aa11e90)](https://huggingface.co/spaces/roxky/g4f-new)
**Is a proof-of-concept API package for multi-provider AI requests. It showcases features such as:**

- Load balancing and request flow control.
- Seamless integration with multiple AI providers.
- Comprehensive text and image generation support.

> Explore the [Visit GPT4Free on HuggingFace Space](https://huggingface.co/spaces/roxky/g4f-new) for a hosted version or [Duplicate GPT4Free Space](https://huggingface.co/spaces/roxky/g4f-new?duplicate=true) it for personal use.

---

## 📚 目录
   - [🆕 最新动态](#-最新动态)
   - [📚 目录](#-目录)
   - [⚡️ 开始使用](#-开始使用)
      - [🛠 安装](#-安装)
         - [🐳 使用Docker](#-使用docker)
         - [🪟 Windows指南(.exe)](#-windows指南exe)
         - [🐍 Python安装](#-python安装)
  - [💡 使用方法](#-使用方法)
     - [📝 文本生成](#-文本生成)
     - [🎨 图像生成](#-图像生成)
     - [🌐 Web界面](#-web界面)
     - [🖥️ 本地推理](docs/local.md)
     - [🤖 接口API](#-接口api)
     - [🛠️ 配置](docs/configuration.md)
     - [📱 在智能手机上运行](#-在智能手机上运行)
     - [📘 Python API完整文档](#-python-api完整文档)
  - [🚀 Providers and Models](docs/providers-and-models.md)
  - [🔗 Powered by gpt4free](#-powered-by-gpt4free)
  - [🤝 Contribute](#-contribute)
     - [如何创建新的提供商?](#guide-如何创建新的提供商)
     - [AI如何帮助我编写代码?](#guide-ai如何帮助我编写代码)
   - [🙌 Contributors](#-contributors)
   - [©️ Copyright](#-copyright)
  - [⭐ Star History](#-star-history)
  - [📄 License](#-license)

---

## ⚡️ 开始使用

## 🛠 安装

### 🐳 使用Docker
1. **安装Docker:** [下载并安装Docker](https://docs.docker.com/get-docker/)。
2. **设置目录:** 在运行容器之前，请确保必要的数据目录存在或可以创建。例如，您可以通过运行以下命令创建并设置这些目录的所有权：
```bash
mkdir -p ${PWD}/har_and_cookies ${PWD}/generated_images
sudo chown -R 1200:1201 ${PWD}/har_and_cookies ${PWD}/generated_images
```
3. **运行Docker容器:** 使用以下命令拉取最新镜像并启动容器（仅x64）：
```bash
docker pull hlohaus789/g4f
docker run -p 8080:8080 -p 7900:7900 \
  --shm-size="2g" \
  -v ${PWD}/har_and_cookies:/app/har_and_cookies \
  -v ${PWD}/generated_images:/app/generated_images \
  hlohaus789/g4f:latest
```

4. **运行Slim Docker镜像:** 使用以下命令运行Slim Docker镜像。此命令还会在启动时更新`g4f`包并安装任何其他依赖项：（x64和arm64）
```bash
mkdir -p ${PWD}/har_and_cookies ${PWD}/generated_images
chown -R 1000:1000 ${PWD}/har_and_cookies ${PWD}/generated_images
docker run \
  -p 1337:1337 \
  -v ${PWD}/har_and_cookies:/app/har_and_cookies \
  -v ${PWD}/generated_images:/app/generated_images \
  hlohaus789/g4f:latest-slim \
  rm -r -f /app/g4f/ \
  && pip install -U g4f[slim] \
  && python -m g4f --debug
```
 
5. **访问客户端界面:**
   - **要使用包含的客户端，请访问:** [http://localhost:8080/chat/](http://localhost:8080/chat/)
   - **或将客户端的API基础设置为:** [http://localhost:8080/v1](http://localhost:8080/v1)

6. **（可选）提供商登录:**
   如果需要，您可以在此处访问容器的桌面：http://localhost:7900/?autoconnect=1&resize=scale&password=secret 以进行提供商登录。

---

### 🪟 Windows指南(.exe)
为了确保我们的应用程序能够顺利运行，请按照以下说明进行操作。这些步骤旨在指导您在Windows操作系统上完成安装过程。

**安装步骤:**
1. **下载应用程序:** 访问我们的[发布页面](https://github.com/xtekky/gpt4free/releases/tag/0.4.2.0)并下载最新版本的应用程序，名为`g4f.exe.zip`。
2. **文件放置:** 下载后，在您的下载文件夹中找到`.zip`文件。将其解压缩到您系统上选择的目录，然后执行`g4f.exe`文件以运行应用程序。
3. **打开GUI:** 该应用程序启动一个带有GUI的Web服务器。打开您喜欢的浏览器并导航到[http://localhost:8080/chat/](http://localhost:8080/chat/)以访问应用程序界面。
4. **防火墙配置（热修复）:** 安装后，可能需要调整Windows防火墙设置以允许应用程序正常运行。为此，请访问Windows防火墙设置并允许应用程序。

通过遵循这些步骤，您应该能够成功在Windows系统上安装和运行应用程序。如果在安装过程中遇到任何问题，请参阅我们的问题跟踪器或尝试通过Discord获取帮助。

---

### 🐍 Python安装

#### 先决条件:
1. 从[python.org](https://www.python.org/downloads/)安装Python 3.10+。
2. 为某些提供商安装Google Chrome。

#### 使用PyPI安装:
```bash
pip install -U g4f[all]
```

> 如何仅安装部分或禁用部分？**使用部分需求:** [/docs/requirements](docs/requirements.md)

#### 从源代码安装:
```bash
git clone https://github.com/xtekky/gpt4free.git
cd gpt4free
pip install -r requirements.txt
```

> 如何使用git加载项目并安装项目需求？**阅读本教程并按步骤操作:** [/docs/git](docs/git.md)

---

## 💡 使用方法

### 📝 文本生成
```python
from g4f.client import Client

client = Client()
response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": "Hello"}],
    web_search=False
)
print(response.choices[0].message.content)
```
```
Hello! How can I assist you today?
```

### 🎨 图像生成
```python
from g4f.client import Client

client = Client()
response = client.images.generate(
    model="flux",
    prompt="a white siamese cat",
    response_format="url"
)

print(f"Generated image URL: {response.data[0].url}")
```
[![Image with cat](/docs/images/cat.jpeg)](docs/client.md)

### 🌐 Web界面
**使用Python运行GUI:**
```python
from g4f.gui import run_gui

run_gui()
```
**通过CLI运行（启动Flask服务器）:**
```bash
python -m g4f.cli gui --port 8080 --debug
```
**或者，启动FastAPI服务器:**
```bash
python -m g4f --port 8080 --debug
```

> **了解更多关于GUI的信息:** 有关如何设置、配置和使用GPT4Free GUI的详细说明，请参阅[GUI文档](docs/gui.md)。本指南包括提供商选择、管理对话、使用高级功能（如语音识别）等的详细步骤。

---

### 🤖 接口API

**接口API**通过G4F实现与OpenAI服务的无缝集成，使您能够部署高效的AI解决方案。

- **文档:** [接口API文档](docs/interference-api.md)
- **端点:** `http://localhost:1337/v1`
- **Swagger UI:** 通过Swagger UI在`http://localhost:1337/docs`浏览OpenAPI文档
- **提供商选择:** [如何指定提供商?](docs/selecting_a_provider.md)

此API设计为简便实施，并增强与其他OpenAI集成的兼容性。

---

### 📱 在智能手机上运行
在智能手机上运行Web UI，方便随时随地访问。查看专门的指南，了解如何设置和使用手机上的GUI：[在智能手机上运行指南](docs/guides/phone.md)

---

#### **📘 Python API完整文档**
   - **G4F的客户端API:** [/docs/client](docs/client.md)
   - **G4F的AsyncClient API:** [/docs/async_client](docs/async_client.md)
   - **G4F的Requests API:** [/docs/requests](docs/requests.md)
   - **G4F的File API:** [/docs/file](docs/file.md)
   - **G4F的PydanticAI和LangChain集成:** [/docs/pydantic_ai](docs/pydantic_ai.md)
   - **使用python模块的旧版API:** [/docs/legacy](docs/legacy.md)
   - **G4F - 媒体文档** [/docs/media](/docs/media.md) *(新)*

---

## 🔗 Powered by gpt4free

<table>
  <thead align="center">
    <tr border: none;>
      <td>
        <b>🎁 Projects</b>
      </td>
      <td>
        <b>⭐ Stars</b>
      </td>
      <td>
        <b>📚 Forks</b>
      </td>
      <td>
        <b>🛎 Issues</b>
      </td>
      <td>
        <b>📬 Pull requests</b>
      </td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <a href="https://github.com/xtekky/gpt4free">
          <b>gpt4free</b>
        </a>
      </td>
      <td>
        <a href="https://github.com/xtekky/gpt4free/stargazers">
          <img alt="Stars" src="https://img.shields.io/github/stars/xtekky/gpt4free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/xtekky/gpt4free/network/members">
          <img alt="Forks" src="https://img.shields.io/github/forks/xtekky/gpt4free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/xtekky/gpt4free/issues">
          <img alt="Issues" src="https://img.shields.io/github/issues/xtekky/gpt4free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/xtekky/gpt4free/pulls">
          <img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/xtekky/gpt4free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
    </tr>
    <td>
      <a href="https://github.com/xiangsx/gpt4free-ts">
        <b>gpt4free-ts</b>
      </a>
    </td>
    <td>
      <a href="https://github.com/xiangsx/gpt4free-ts/stargazers">
        <img alt="Stars" src="https://img.shields.io/github/stars/xiangsx/gpt4free-ts?style=flat-square&labelColor=343b41" />
      </a>
    </td>
    <td>
      <a href="https://github.com/xiangsx/gpt4free-ts/network/members">
        <img alt="Forks" src="https://img.shields.io/github/forks/xiangsx/gpt4free-ts?style=flat-square&labelColor=343b41" />
      </a>
    </td>
    <td>
      <a href="https://github.com/xiangsx/gpt4free-ts/issues">
        <img alt="Issues" src="https://img.shields.io/github/issues/xiangsx/gpt4free-ts?style=flat-square&labelColor=343b41" />
      </a>
    </td>
    <td>
      <a href="https://github.com/xiangsx/gpt4free-ts/pulls">
        <img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/xiangsx/gpt4free-ts?style=flat-square&labelColor=343b41" />
      </a>
    </td>
    </tr>
    <tr>
      <td>
        <a href="https://github.com/zukixa/cool-ai-stuff/">
          <b>Free AI API's & Potential Providers List</b>
        </a>
      </td>
      <td>
        <a href="https://github.com/zukixa/cool-ai-stuff/stargazers">
          <img alt="Stars" src="https://img.shields.io/github/stars/zukixa/cool-ai-stuff?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/zukixa/cool-ai-stuff/network/members">
          <img alt="Forks" src="https://img.shields.io/github/forks/zukixa/cool-ai-stuff?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/zukixa/cool-ai-stuff/issues">
          <img alt="Issues" src="https://img.shields.io/github/issues/zukixa/cool-ai-stuff?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/zukixa/cool-ai-stuff/pulls">
          <img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/zukixa/cool-ai-stuff?style=flat-square&labelColor=343b41" />
        </a>
      </td>
    </tr>
    <tr>
    <tr>
      <td>
        <a href="https://github.com/xtekky/chatgpt-clone">
          <b>ChatGPT-Clone</b>
        </a>
      </td>
      <td>
        <a href="https://github.com/xtekky/chatgpt-clone/stargazers">
          <img alt="Stars" src="https://img.shields.io/github/stars/xtekky/chatgpt-clone?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/xtekky/chatgpt-clone/network/members">
          <img alt="Forks" src="https://img.shields.io/github/forks/xtekky/chatgpt-clone?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/xtekky/chatgpt-clone/issues">
          <img alt="Issues" src="https://img.shields.io/github/issues/xtekky/chatgpt-clone?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/xtekky/chatgpt-clone/pulls">
          <img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/xtekky/chatgpt-clone?style=flat-square&labelColor=343b41" />
        </a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="https://github.com/mishalhossin/Discord-Chatbot-Gpt4Free">
          <b>Ai agent</b>
        </a>
      </td>
      <td>
        <a href="https://github.com/Josh-XT/AGiXT/stargazers">
          <img alt="Stars" src="https://img.shields.io/github/stars/mishalhossin/Discord-Chatbot-Gpt4Free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Josh-XT/AGiXT/network/members">
          <img alt="Forks" src="https://img.shields.io/github/forks/mishalhossin/Discord-Chatbot-Gpt4Free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Josh-XT/AGiXT/issues">
          <img alt="Issues" src="https://img.shields.io/github/issues/mishalhossin/Discord-Chatbot-Gpt4Free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Josh-XT/AGiXT/pulls">
          <img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/mishalhossin/Discord-Chatbot-Gpt4Free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="https://github.com/mishalhossin/Discord-Chatbot-Gpt4Free">
          <b>ChatGpt Discord Bot</b>
        </a>
      </td>
      <td>
        <a href="https://github.com/mishalhossin/Discord-Chatbot-Gpt4Free/stargazers">
          <img alt="Stars" src="https://img.shields.io/github/stars/mishalhossin/Discord-Chatbot-Gpt4Free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/mishalhossin/Discord-Chatbot-Gpt4Free/network/members">
          <img alt="Forks" src="https://img.shields.io/github/forks/mishalhossin/Discord-Chatbot-Gpt4Free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/mishalhossin/Discord-Chatbot-Gpt4Free/issues">
          <img alt="Issues" src="https://img.shields.io/github/issues/mishalhossin/Discord-Chatbot-Gpt4Free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/mishalhossin/Coding-Chatbot-Gpt4Free/pulls">
          <img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/mishalhossin/Discord-Chatbot-Gpt4Free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
    <tr>
    <tr>
      <td>
        <a href="https://github.com/Zero6992/chatGPT-discord-bot">
          <b>chatGPT-discord-bot</b>
        </a>
      </td>
      <td>
        <a href="https://github.com/Zero6992/chatGPT-discord-bot/stargazers">
          <img alt="Stars" src="https://img.shields.io/github/stars/Zero6992/chatGPT-discord-bot?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Zero6992/chatGPT-discord-bot/network/members">
          <img alt="Forks" src="https://img.shields.io/github/forks/Zero6992/chatGPT-discord-bot?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Zero6992/chatGPT-discord-bot/issues">
          <img alt="Issues" src="https://img.shields.io/github/issues/Zero6992/chatGPT-discord-bot?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Zero6992/chatGPT-discord-bot/pulls">
          <img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/Zero6992/chatGPT-discord-bot?style=flat-square&labelColor=343b41" />
        </a>
      </td>
    <tr>
      <td>
        <a href="https://github.com/SamirXR/Nyx-Bot">
          <b>Nyx-Bot (Discord)</b>
        </a>
      </td>
      <td>
        <a href="https://github.com/SamirXR/Nyx-Bot/stargazers">
          <img alt="Stars" src="https://img.shields.io/github/stars/SamirXR/Nyx-Bot?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/SamirXR/Nyx-Bot/network/members">
          <img alt="Forks" src="https://img.shields.io/github/forks/SamirXR/Nyx-Bot?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/SamirXR/Nyx-Bot/issues">
          <img alt="Issues" src="https://img.shields.io/github/issues/SamirXR/Nyx-Bot?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/SamirXR/Nyx-Bot/pulls">
          <img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/SamirXR/Nyx-Bot?style=flat-square&labelColor=343b41" />
        </a>
      </td>
    </tr>
    </tr>
    <tr>
      <td>
        <a href="https://github.com/MIDORIBIN/langchain-gpt4free">
          <b>LangChain gpt4free</b>
        </a>
      </td>
      <td>
        <a href="https://github.com/MIDORIBIN/langchain-gpt4free/stargazers">
          <img alt="Stars" src="https://img.shields.io/github/stars/MIDORIBIN/langchain-gpt4free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/MIDORIBIN/langchain-gpt4free/network/members">
          <img alt="Forks" src="https://img.shields.io/github/forks/MIDORIBIN/langchain-gpt4free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/MIDORIBIN/langchain-gpt4free/issues">
          <img alt="Issues" src="https://img.shields.io/github/issues/MIDORIBIN/langchain-gpt4free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/MIDORIBIN/langchain-gpt4free/pulls">
          <img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/MIDORIBIN/langchain-gpt4free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="https://github.com/HexyeDEV/Telegram-Chatbot-Gpt4Free">
          <b>ChatGpt Telegram Bot</b>
        </a>
      </td>
      <td>
        <a href="https://github.com/HexyeDEV/Telegram-Chatbot-Gpt4Free/stargazers">
          <img alt="Stars" src="https://img.shields.io/github/stars/HexyeDEV/Telegram-Chatbot-Gpt4Free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/HexyeDEV/Telegram-Chatbot-Gpt4Free/network/members">
          <img alt="Forks" src="https://img.shields.io/github/forks/HexyeDEV/Telegram-Chatbot-Gpt4Free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/HexyeDEV/Telegram-Chatbot-Gpt4Free/issues">
          <img alt="Issues" src="https://img.shields.io/github/issues/HexyeDEV/Telegram-Chatbot-Gpt4Free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/HexyeDEV/Telegram-Chatbot-Gpt4Free/pulls">
          <img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/HexyeDEV/Telegram-Chatbot-Gpt4Free?style=flat-square&labelColor=343b41" />
        </a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="https://github.com/Lin-jun-xiang/chatgpt-line-bot">
          <b>ChatGpt Line Bot</b>
        </a>
      </td>
      <td>
        <a href="https://github.com/Lin-jun-xiang/chatgpt-line-bot/stargazers">
          <img alt="Stars" src="https://img.shields.io/github/stars/Lin-jun-xiang/chatgpt-line-bot?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Lin-jun-xiang/chatgpt-line-bot/network/members">
          <img alt="Forks" src="https://img.shields.io/github/forks/Lin-jun-xiang/chatgpt-line-bot?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Lin-jun-xiang/chatgpt-line-bot/issues">
          <img alt="Issues" src="https://img.shields.io/github/issues/Lin-jun-xiang/chatgpt-line-bot?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Lin-jun-xiang/chatgpt-line-bot/pulls">
          <img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/Lin-jun-xiang/chatgpt-line-bot?style=flat-square&labelColor=343b41" />
        </a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="https://github.com/Lin-jun-xiang/action-translate-readme">
          <b>Action Translate Readme</b>
        </a>
      </td>
      <td>
        <a href="https://github.com/Lin-jun-xiang/action-translate-readme/stargazers">
          <img alt="Stars" src="https://img.shields.io/github/stars/Lin-jun-xiang/action-translate-readme?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Lin-jun-xiang/action-translate-readme/network/members">
          <img alt="Forks" src="https://img.shields.io/github/forks/Lin-jun-xiang/action-translate-readme?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Lin-jun-xiang/action-translate-readme/issues">
          <img alt="Issues" src="https://img.shields.io/github/issues/Lin-jun-xiang/action-translate-readme?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Lin-jun-xiang/action-translate-readme/pulls">
          <img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/Lin-jun-xiang/action-translate-readme?style=flat-square&labelColor=343b41" />
        </a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="https://github.com/Lin-jun-xiang/docGPT-streamlit">
          <b>Langchain Document GPT</b>
        </a>
      </td>
      <td>
        <a href="https://github.com/Lin-jun-xiang/docGPT-streamlit/stargazers">
          <img alt="Stars" src="https://img.shields.io/github/stars/Lin-jun-xiang/docGPT-streamlit?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Lin-jun-xiang/docGPT-streamlit/network/members">
          <img alt="Forks" src="https://img.shields.io/github/forks/Lin-jun-xiang/docGPT-streamlit?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Lin-jun-xiang/docGPT-streamlit/issues">
          <img alt="Issues" src="https://img.shields.io/github/issues/Lin-jun-xiang/docGPT-streamlit?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Lin-jun-xiang/docGPT-streamlit/pulls">
          <img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/Lin-jun-xiang/docGPT-streamlit?style=flat-square&labelColor=343b41" />
        </a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="https://github.com/Simatwa/python-tgpt">
          <b>python-tgpt</b>
        </a>
      </td>
      <td>
        <a href="https://github.com/Simatwa/python-tgpt/stargazers">
          <img alt="Stars" src="https://img.shields.io/github/stars/Simatwa/python-tgpt?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Simatwa/python-tgpt/network/members">
          <img alt="Forks" src="https://img.shields.io/github/forks/Simatwa/python-tgpt?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Simatwa/python-tgpt/issues">
          <img alt="Issues" src="https://img.shields.io/github/issues/Simatwa/python-tgpt?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/Simatwa/python-tgpt/pulls">
          <img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/Simatwa/python-tgpt?style=flat-square&labelColor=343b41" />
        </a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="https://github.com/zachey01/gpt4free.js">
          <b>GPT4js</b>
        </a>
      </td>
      <td>
        <a href="https://github.com/zachey01/gpt4free.js/stargazers">
          <img alt="Stars" src="https://img.shields.io/github/stars/zachey01/gpt4free.js?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/zachey01/gpt4free.js/network/members">
          <img alt="Forks" src="https://img.shields.io/github/forks/zachey01/gpt4free.js?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/zachey01/gpt4free.js/issues">
          <img alt="Issues" src="https://img.shields.io/github/issues/zachey01/gpt4free.js?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/zachey01/gpt4free.js/pulls">
          <img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/zachey01/gpt4free.js?style=flat-square&labelColor=343b41" />
        </a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="https://github.com/yjg30737/pyqt-openai">
          <b>VividNode (pyqt-openai)</b>
        </a>
      </td>
      <td>
        <a href="https://github.com/yjg30737/pyqt-openai/stargazers">
          <img alt="Stars" src="https://img.shields.io/github/stars/yjg30737/pyqt-openai?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/yjg30737/pyqt-openai/network/members">
          <img alt="Forks" src="https://img.shields.io/github/forks/yjg30737/pyqt-openai?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/yjg30737/pyqt-openai/issues">
          <img alt="Issues" src="https://img.shields.io/github/issues/yjg30737/pyqt-openai?style=flat-square&labelColor=343b41" />
        </a>
      </td>
      <td>
        <a href="https://github.com/yjg30737/pyqt-openai/pulls">
          <img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/yjg30737/pyqt-openai?style=flat-square&labelColor=343b41" />
        </a>
      </td>
    </tr>
  </tbody>
</table>



## 🤝 Contribute
We welcome contributions from the community. Whether you're adding new providers or features, or simply fixing typos and making small improvements, your input is valued. Creating a pull request is all it takes – our co-pilot will handle the code review process. Once all changes have been addressed, we'll merge the pull request into the main branch and release the updates at a later time.

###### Guide: 如何创建新的提供商?
   - **阅读:** [创建提供商指南](docs/guides/create_provider.md)

###### Guide: AI如何帮助我编写代码?
   - **阅读:** [AI帮助指南](docs/guides/help_me.md)



## Contributors
A list of all contributors is available [here](https://github.com/xtekky/gpt4free/graphs/contributors)

<a href="https://github.com/xtekky" target="_blank"><img src="https://avatars.githubusercontent.com/u/98614666?v=4&s=45" width="45" title="xtekky"></a>
<a href="https://github.com/hlohaus" target="_blank"><img src="https://avatars.githubusercontent.com/u/983577?v=4&s=45" width="45" title="hlohaus"></a>
<a href="https://github.com/kqlio67" target="_blank"><img src="https://avatars.githubusercontent.com/u/166700875?v=4&s=45" width="45" title="kqlio67"></a>
<a href="https://github.com/bagusindrayana" target="_blank"><img src="https://avatars.githubusercontent.com/u/36830534?v=4&s=45" width="45" title="bagusindrayana"></a>
<a href="https://github.com/sudouser777" target="_blank"><img src="https://avatars.githubusercontent.com/u/22415463?v=4&s=45" width="45" title="sudouser777"></a>
<a href="https://github.com/thatlukinhasguy1" target="_blank"><img src="https://avatars.githubusercontent.com/u/139662282?v=4&s=45" width="45" title="thatlukinhasguy1"></a>
<a href="https://github.com/Commenter123321" target="_blank"><img src="https://avatars.githubusercontent.com/u/36051603?v=4&s=45" width="45" title="Commenter123321"></a>
<a href="https://github.com/DanielShemesh" target="_blank"><img src="https://avatars.githubusercontent.com/u/20585236?v=4&s=45" width="45" title="DanielShemesh"></a>
<a href="https://github.com/Luneye" target="_blank"><img src="https://avatars.githubusercontent.com/u/73485421?v=4&s=45" width="45" title="Luneye"></a>
<a href="https://github.com/foxfire52" target="_blank"><img src="https://avatars.githubusercontent.com/u/185073927?v=4&s=45" width="45" title="foxfire52"></a>
<a href="https://github.com/ezerinz" target="_blank"><img src="https://avatars.githubusercontent.com/u/100193740?v=4&s=45" width="45" title="ezerinz"></a>
<a href="https://github.com/enganese" target="_blank"><img src="https://avatars.githubusercontent.com/u/69082498?v=4&s=45" width="45" title="enganese"></a>
<a href="https://github.com/Lin-jun-xiang" target="_blank"><img src="https://avatars.githubusercontent.com/u/63782903?v=4&s=45" width="45" title="Lin-jun-xiang"></a>
<a href="https://github.com/nullstreak" target="_blank"><img src="https://avatars.githubusercontent.com/u/139914347?v=4&s=45" width="45" title="nullstreak"></a>
<a href="https://github.com/valerii-chirkov" target="_blank"><img src="https://avatars.githubusercontent.com/u/81074936?v=4&s=45" width="45" title="valerii-chirkov"></a>
<a href="https://github.com/MIDORIBIN" target="_blank"><img src="https://avatars.githubusercontent.com/u/25425217?v=4&s=45" width="45" title="MIDORIBIN"></a>
<a href="https://github.com/repollo" target="_blank"><img src="https://avatars.githubusercontent.com/u/2671466?v=4&s=45" width="45" title="repollo"></a>
<a href="https://github.com/hpsj" target="_blank"><img src="https://avatars.githubusercontent.com/u/54535414?v=4&s=45" width="45" title="hpsj"></a>
<a href="https://github.com/taiyi747" target="_blank"><img src="https://avatars.githubusercontent.com/u/63543716?v=4&s=45" width="45" title="taiyi747"></a>
<a href="https://github.com/zukixa" target="_blank"><img src="https://avatars.githubusercontent.com/u/56563509?v=4&s=45" width="45" title="zukixa"></a>
<a href="https://github.com/ostix360" target="_blank"><img src="https://avatars.githubusercontent.com/u/55257054?v=4&s=45" width="45" title="ostix360"></a>
<a href="https://github.com/WdR-Tech" target="_blank"><img src="https://avatars.githubusercontent.com/u/143020293?v=4&s=45" width="45" title="WdR-Tech"></a>
<a href="https://github.com/HexyeDEV" target="_blank"><img src="https://avatars.githubusercontent.com/u/65314629?v=4&s=45" width="45" title="HexyeDEV"></a>
<a href="https://github.com/9fo" target="_blank"><img src="https://avatars.githubusercontent.com/u/71867245?v=4&s=45" width="45" title="9fo"></a>
<a href="https://github.com/devAdityaa" target="_blank"><img src="https://avatars.githubusercontent.com/u/77636021?v=4&s=45" width="45" title="devAdityaa"></a>
<a href="https://github.com/24rr" target="_blank"><img src="https://avatars.githubusercontent.com/u/109844019?v=4&s=45" width="45" title="24rr"></a>
<a href="https://github.com/zeng-rr" target="_blank"><img src="https://avatars.githubusercontent.com/u/47846202?v=4&s=45" width="45" title="zeng-rr"></a>
<a href="https://github.com/rkihacker" target="_blank"><img src="https://avatars.githubusercontent.com/u/182319878?v=4&s=45" width="45" title="rkihacker"></a>
<a href="https://github.com/naa7" target="_blank"><img src="https://avatars.githubusercontent.com/u/44613678?v=4&s=45" width="45" title="naa7"></a>
<a href="https://github.com/ramon-victor" target="_blank"><img src="https://avatars.githubusercontent.com/u/13617054?v=4&s=45" width="45" title="ramon-victor"></a>
<a href="https://github.com/eltociear" target="_blank"><img src="https://avatars.githubusercontent.com/u/22633385?v=4&s=45" width="45" title="eltociear"></a>
<a href="https://github.com/kggn" target="_blank"><img src="https://avatars.githubusercontent.com/u/95663228?v=4&s=45" width="45" title="kggn"></a>
<a href="https://github.com/xiangsx" target="_blank"><img src="https://avatars.githubusercontent.com/u/29322721?v=4&s=45" width="45" title="xiangsx"></a>
<a href="https://github.com/ggindinson" target="_blank"><img src="https://avatars.githubusercontent.com/u/97807772?v=4&s=45" width="45" title="ggindinson"></a>
<a href="https://github.com/ahobsonsayers" target="_blank"><img src="https://avatars.githubusercontent.com/u/32173585?v=4&s=45" width="45" title="ahobsonsayers"></a>
<a href="https://github.com/mache102" target="_blank"><img src="https://avatars.githubusercontent.com/u/91365155?v=4&s=45" width="45" title="mache102"></a>
<a href="https://github.com/kogakisaki" target="_blank"><img src="https://avatars.githubusercontent.com/u/95165750?v=4&s=45" width="45" title="kogakisaki"></a>
<a href="https://github.com/Andrew-Tsegaye" target="_blank"><img src="https://avatars.githubusercontent.com/u/91322467?v=4&s=45" width="45" title="Andrew-Tsegaye"></a>
<a href="https://github.com/omidima" target="_blank"><img src="https://avatars.githubusercontent.com/u/47784584?v=4&s=45" width="45" title="omidima"></a>
<a href="https://github.com/nonk123" target="_blank"><img src="https://avatars.githubusercontent.com/u/43842467?v=4&s=45" width="45" title="nonk123"></a>
<a href="https://github.com/MaxKUlish1" target="_blank"><img src="https://avatars.githubusercontent.com/u/93388714?v=4&s=45" width="45" title="MaxKUlish1"></a>
<a href="https://github.com/AymaneHrouch" target="_blank"><img src="https://avatars.githubusercontent.com/u/36491424?v=4&s=45" width="45" title="AymaneHrouch"></a>
<a href="https://github.com/Eikosa" target="_blank"><img src="https://avatars.githubusercontent.com/u/20538090?v=4&s=45" width="45" title="Eikosa"></a>
<a href="https://github.com/localagi" target="_blank"><img src="https://avatars.githubusercontent.com/u/132956819?v=4&s=45" width="45" title="localagi"></a>
<a href="https://github.com/thebigbone" target="_blank"><img src="https://avatars.githubusercontent.com/u/95130644?v=4&s=45" width="45" title="thebigbone"></a>
<a href="https://github.com/kailust" target="_blank"><img src="https://avatars.githubusercontent.com/u/82623773?v=4&s=45" width="45" title="kailust"></a>
<a href="https://github.com/ading2210" target="_blank"><img src="https://avatars.githubusercontent.com/u/71154407?v=4&s=45" width="45" title="ading2210"></a>
<a href="https://github.com/Zero6992" target="_blank"><img src="https://avatars.githubusercontent.com/u/89479282?v=4&s=45" width="45" title="Zero6992"></a>
<a href="https://github.com/mishl-dev" target="_blank"><img src="https://avatars.githubusercontent.com/u/91066601?v=4&s=45" width="45" title="mishl-dev"></a>
<a href="https://github.com/ElonGaties" target="_blank"><img src="https://avatars.githubusercontent.com/u/59313695?v=4&s=45" width="45" title="ElonGaties"></a>
<a href="https://github.com/TotoB12" target="_blank"><img src="https://avatars.githubusercontent.com/u/91705868?v=4&s=45" width="45" title="TotoB12"></a>
<a href="https://github.com/malivinayak" target="_blank"><img src="https://avatars.githubusercontent.com/u/66154908?v=4&s=45" width="45" title="malivinayak"></a>
<a href="https://github.com/Zedai00" target="_blank"><img src="https://avatars.githubusercontent.com/u/33319711?v=4&s=45" width="45" title="Zedai00"></a>
<a href="https://github.com/catmeowjiao" target="_blank"><img src="https://avatars.githubusercontent.com/u/138079152?v=4&s=45" width="45" title="catmeowjiao"></a>
<a href="https://github.com/cifer-sudo" target="_blank"><img src="https://avatars.githubusercontent.com/u/60644739?v=4&s=45" width="45" title="cifer-sudo"></a>
<a href="https://github.com/eminemkun" target="_blank"><img src="https://avatars.githubusercontent.com/u/49590289?v=4&s=45" width="45" title="eminemkun"></a>
<a href="https://github.com/kafmws" target="_blank"><img src="https://avatars.githubusercontent.com/u/33590879?v=4&s=45" width="45" title="kafmws"></a>
<a href="https://github.com/najam-tariq" target="_blank"><img src="https://avatars.githubusercontent.com/u/103676132?v=4&s=45" width="45" title="najam-tariq"></a>
<a href="https://github.com/ochen1" target="_blank"><img src="https://avatars.githubusercontent.com/u/59662605?v=4&s=45" width="45" title="ochen1"></a>
<a href="https://github.com/r1di" target="_blank"><img src="https://avatars.githubusercontent.com/u/33724815?v=4&s=45" width="45" title="r1di"></a>
<a href="https://github.com/sagadav" target="_blank"><img src="https://avatars.githubusercontent.com/u/42406802?v=4&s=45" width="45" title="sagadav"></a>
<a href="https://github.com/snyk-bot" target="_blank"><img src="https://avatars.githubusercontent.com/u/19733683?v=4&s=45" width="45" title="snyk-bot"></a>
<a href="https://github.com/vatva691" target="_blank"><img src="https://avatars.githubusercontent.com/u/30290559?v=4&s=45" width="45" title="vatva691"></a>
<a href="https://github.com/Qustelm" target="_blank"><img src="https://avatars.githubusercontent.com/u/83110161?v=4&s=45" width="45" title="Qustelm"></a>
<a href="https://github.com/HyiKi" target="_blank"><img src="https://avatars.githubusercontent.com/u/55942998?v=4&s=45" width="45" title="HyiKi"></a>
<a href="https://github.com/0dminnimda" target="_blank"><img src="https://avatars.githubusercontent.com/u/52697657?v=4&s=45" width="45" title="0dminnimda"></a>
<a href="https://github.com/Akash98Sky" target="_blank"><img src="https://avatars.githubusercontent.com/u/37451227?v=4&s=45" width="45" title="Akash98Sky"></a>
<a href="https://github.com/adeyinkaezra123" target="_blank"><img src="https://avatars.githubusercontent.com/u/65364356?v=4&s=45" width="45" title="adeyinkaezra123"></a>
<a href="https://github.com/Giancarlo-Ma" target="_blank"><img src="https://avatars.githubusercontent.com/u/65126107?v=4&s=45" width="45" title="Giancarlo-Ma"></a>
<a href="https://github.com/gran4" target="_blank"><img src="https://avatars.githubusercontent.com/u/80655391?v=4&s=45" width="45" title="gran4"></a>
<a href="https://github.com/guspan-tanadi" target="_blank"><img src="https://avatars.githubusercontent.com/u/36249910?v=4&s=45" width="45" title="guspan-tanadi"></a>
<a href="https://github.com/oubrax" target="_blank"><img src="https://avatars.githubusercontent.com/u/72103863?v=4&s=45" width="45" title="oubrax"></a>
<a href="https://github.com/hansipie" target="_blank"><img src="https://avatars.githubusercontent.com/u/5460714?v=4&s=45" width="45" title="hansipie"></a>
<a href="https://github.com/GetTuh" target="_blank"><img src="https://avatars.githubusercontent.com/u/27581581?v=4&s=45" width="45" title="GetTuh"></a>
<a href="https://github.com/kushal34712" target="_blank"><img src="https://avatars.githubusercontent.com/u/98145879?v=4&s=45" width="45" title="kushal34712"></a>
<a href="https://github.com/Fubge" target="_blank"><img src="https://avatars.githubusercontent.com/u/115476150?v=4&s=45" width="45" title="Fubge"></a>
<a href="https://github.com/Niapoll" target="_blank"><img src="https://avatars.githubusercontent.com/u/64135936?v=4&s=45" width="45" title="Niapoll"></a>
<a href="https://github.com/OmiiiDev" target="_blank"><img src="https://avatars.githubusercontent.com/u/103533638?v=4&s=45" width="45" title="OmiiiDev"></a>
<a href="https://github.com/RasyiidWho" target="_blank"><img src="https://avatars.githubusercontent.com/u/19422415?v=4&s=45" width="45" title="RasyiidWho"></a>
<a href="https://github.com/RavenOwO" target="_blank"><img src="https://avatars.githubusercontent.com/u/118295106?v=4&s=45" width="45" title="RavenOwO"></a>
<a href="https://github.com/anonymousx97" target="_blank"><img src="https://avatars.githubusercontent.com/u/88324835?v=4&s=45" width="45" title="anonymousx97"></a>
<a href="https://github.com/krjordan" target="_blank"><img src="https://avatars.githubusercontent.com/u/10234150?v=4&s=45" width="45" title="krjordan"></a>
<a href="https://github.com/SilverMarcs" target="_blank"><img src="https://avatars.githubusercontent.com/u/77480421?v=4&s=45" width="45" title="SilverMarcs"></a>
<a href="https://github.com/Yusufibin" target="_blank"><img src="https://avatars.githubusercontent.com/u/71589435?v=4&s=45" width="45" title="Yusufibin"></a>
<a href="https://github.com/yuri-val" target="_blank"><img src="https://avatars.githubusercontent.com/u/15129796?v=4&s=45" width="45" title="yuri-val"></a>
<a href="https://github.com/yousefnegmeldin" target="_blank"><img src="https://avatars.githubusercontent.com/u/96620955?v=4&s=45" width="45" title="yousefnegmeldin"></a>
<a href="https://github.com/perklet" target="_blank"><img src="https://avatars.githubusercontent.com/u/1035487?v=4&s=45" width="45" title="perklet"></a>
<a href="https://github.com/varshney-yash" target="_blank"><img src="https://avatars.githubusercontent.com/u/107148830?v=4&s=45" width="45" title="varshney-yash"></a>
<a href="https://github.com/Yoxmo" target="_blank"><img src="https://avatars.githubusercontent.com/u/94254616?v=4&s=45" width="45" title="Yoxmo"></a>
<a href="https://github.com/yjg30737" target="_blank"><img src="https://avatars.githubusercontent.com/u/55078043?v=4&s=45" width="45" title="yjg30737"></a>
<a href="https://github.com/williamstein" target="_blank"><img src="https://avatars.githubusercontent.com/u/1276278?v=4&s=45" width="45" title="williamstein"></a>
<a href="https://github.com/ZachKLYeh" target="_blank"><img src="https://avatars.githubusercontent.com/u/105150034?v=4&s=45" width="45" title="ZachKLYeh"></a>
<a href="https://github.com/alvarosoaress" target="_blank"><img src="https://avatars.githubusercontent.com/u/13721147?v=4&s=45" width="45" title="alvarosoaress"></a>
<a href="https://github.com/bruvv" target="_blank"><img src="https://avatars.githubusercontent.com/u/3063928?v=4&s=45" width="45" title="bruvv"></a>
<a href="https://github.com/carlinhoshk" target="_blank"><img src="https://avatars.githubusercontent.com/u/40872405?v=4&s=45" width="45" title="carlinhoshk"></a>
<a href="https://github.com/cckuailong" target="_blank"><img src="https://avatars.githubusercontent.com/u/10824150?v=4&s=45" width="45" title="cckuailong"></a>
<a href="https://github.com/chinmay7016" target="_blank"><img src="https://avatars.githubusercontent.com/u/75988613?v=4&s=45" width="45" title="chinmay7016"></a>
<a href="https://github.com/diaodeng" target="_blank"><img src="https://avatars.githubusercontent.com/u/108243171?v=4&s=45" width="45" title="diaodeng"></a>
<a href="https://github.com/monosans" target="_blank"><img src="https://avatars.githubusercontent.com/u/76561516?v=4&s=45" width="45" title="monosans"></a>
<a href="https://github.com/Ayushpanditmoto" target="_blank"><img src="https://avatars.githubusercontent.com/u/31253617?v=4&s=45" width="45" title="Ayushpanditmoto"></a>
<span></span>
<img src="https://avatars.githubusercontent.com/u/71154407?s=45&v=4" width="45" title="ading2210">
<img src="https://avatars.githubusercontent.com/u/12299238?s=45&v=4" width="45" title="xqdoo00o">
<img src="https://avatars.githubusercontent.com/u/97126670?s=45&v=4" width="45" title="nathanrchn">
<img src="https://avatars.githubusercontent.com/u/81407603?v=4&s=45" width="45" title="dsdanielpark">
<img src="https://avatars.githubusercontent.com/u/55200481?v=4&s=45" width="45" title="missuo">

- The [`Vercel.py`](https://github.com/xtekky/gpt4free/blob/main/g4f/Provider/Vercel.py) file contains code from [vercel-llm-api](https://github.com/ading2210/vercel-llm-api) by [@ading2210](https://github.com/ading2210)
- The [`har_file.py`](https://github.com/xtekky/gpt4free/blob/main/g4f/Provider/openai/har_file.py) has input from [xqdoo00o/ChatGPT-to-API](https://github.com/xqdoo00o/ChatGPT-to-API)
- The [`PerplexityLabs.py`](https://github.com/xtekky/gpt4free/blob/main/g4f/Provider/PerplexityLabs.py) has input from [nathanrchn/perplexityai](https://github.com/nathanrchn/perplexityai)
- The [`Gemini.py`](https://github.com/xtekky/gpt4free/blob/main/g4f/Provider/needs_auth/Gemini.py) has input from [dsdanielpark/Gemini-API](https://github.com/dsdanielpark/Gemini-API)
- The [`MetaAI.py`](https://github.com/xtekky/gpt4free/blob/main/g4f/Provider/MetaAI.py) file contains code from [meta-ai-api](https://github.com/Strvm/meta-ai-api) by [@Strvm](https://github.com/Strvm)
- The [`proofofwork.py`](https://github.com/xtekky/gpt4free/blob/main/g4f/Provider/openai/proofofwork.py) has input from [missuo/FreeGPT35](https://github.com/missuo/FreeGPT35)
- The [`Gemini.py`](https://github.com/xtekky/gpt4free/blob/main/g4f/Provider/needs_auth/Gemini.py) has input from [HanaokaYuzu/Gemini-API](https://github.com/HanaokaYuzu/Gemini-API)

_Having input implies that the AI's code generation utilized it as one of many sources._


## ©️ Copyright

This program is licensed under the [GNU GPL v3](https://www.gnu.org/licenses/gpl-3.0.txt)

```
xtekky/gpt4free: Copyright (C) 2023 xtekky

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
```


## ⭐ Star History

<a href="https://github.com/xtekky/gpt4free/stargazers">
        <img width="500" alt="Star History Chart" src="https://api.star-history.com/svg?repos=xtekky/gpt4free&type=Date">
</a>


## 📄 License

<table>
  <tr>
     <td>
       <p align="center"> <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/93/GPLv3_Logo.svg/1200px-GPLv3_Logo.svg.png" width="80%"></img>
    </td>
    <td> 
      <img src="https://img.shields.io/badge/License-GNU_GPL_v3.0-red.svg"/> <br> 
This project is licensed under <a href="https://github.com/xtekky/gpt4free/blob/main/LICENSE">GNU_GPL_v3.0</a>.
    </td>
  </tr>
</table>

---

<p align="right">(<a href="#top">🔼 Back to top</a>)</p>

