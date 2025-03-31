### G4F - Configuration


## Table of Contents
- [Authentication](#authentication)
- [Cookies Configuration](#cookies-configuration)
- [HAR and Cookie Files](#har-and-cookie-files) 
- [Debug Mode](#debug-mode)
- [Proxy Configuration](#proxy-configuration)


#### Authentication

Refer to the [G4F Authentication Setup Guide](authentication.md) for detailed instructions on setting up authentication.

### Cookies Configuration
Cookies are essential for using Meta AI and Microsoft Designer to create images.
Additionally, cookies are required for the Google Gemini and WhiteRabbitNeo Provider.
From Bing, ensure you have the "\_U" cookie, and from Google, all cookies starting with "\_\_Secure-1PSID" are needed.

**You can pass these cookies directly to the create function or set them using the `set_cookies` method before running G4F:**
```python
from g4f.cookies import set_cookies

set_cookies(".bing.com", {
  "_U": "cookie value"
})

set_cookies(".google.com", {
  "__Secure-1PSID": "cookie value"
})
```
---
### HAR and Cookie Files
**Using .har and Cookie Files**
You can place `.har` and cookie files `.json` in the default `./har_and_cookies` directory. To export a cookie file, use the [EditThisCookie Extension](https://chromewebstore.google.com/detail/editthiscookie/fngmhnnpilhplaeedifhccceomclgfbg) available on the Chrome Web Store.

**Creating .har Files to Capture Cookies**
To capture cookies, you can also create `.har` files. For more details, refer to the next section.

### Changing the Cookies Directory and Loading Cookie Files in Python
**You can change the cookies directory and load cookie files in your Python environment. To set the cookies directory relative to your Python file, use the following code:**
```python
import os.path
from g4f.cookies import set_cookies_dir, read_cookie_files

import g4f.debug
g4f.debug.logging = True

cookies_dir = os.path.join(os.path.dirname(__file__), "har_and_cookies")
set_cookies_dir(cookies_dir)
read_cookie_files(cookies_dir)
```

### Debug Mode
**If you enable debug mode, you will see logs similar to the following:**

```
Read .har file: ./har_and_cookies/you.com.har
Cookies added: 10 from .you.com
Read cookie file: ./har_and_cookies/google.json
Cookies added: 16 from .google.com
```

#### .HAR File for OpenaiChat Provider

##### Generating a .HAR File

**To utilize the OpenaiChat provider, a .har file is required from https://chatgpt.com/. Follow the steps below to create a valid .har file:**
1. Navigate to https://chatgpt.com/ using your preferred web browser and log in with your credentials.
2. Access the Developer Tools in your browser. This can typically be done by right-clicking the page and selecting "Inspect," or by pressing F12 or Ctrl+Shift+I (Cmd+Option+I on a Mac).
3. With the Developer Tools open, switch to the "Network" tab.
4. Reload the website to capture the loading process within the Network tab.
5. Initiate an action in the chat which can be captured in the .har file.
6. Right-click any of the network activities listed and select "Save all as HAR with content" to export the .har file.

##### Storing the .HAR File

- Place the exported .har file in the `./har_and_cookies` directory if you are using Docker. Alternatively, if you are using Python from a terminal, you can store it in a `./har_and_cookies` directory within your current working directory.

> **Note:** Ensure that your .har file is stored securely, as it may contain sensitive information.

### Proxy Configuration
**If you want to hide or change your IP address for the providers, you can set a proxy globally via an environment variable:**

**- On macOS and Linux:**
```bash
export G4F_PROXY="http://host:port"
```

**- On Windows:**
```bash
set G4F_PROXY=http://host:port
```

### G4F - 配置


## 目录
- [认证](#认证)
- [Cookie配置](#cookie配置)
- [HAR和Cookie文件](#har和cookie文件) 
- [调试模式](#调试模式)
- [代理配置](#代理配置)


#### 认证

请参阅[G4F认证设置指南](authentication.md)获取有关设置认证的详细说明。

### Cookie配置
Cookie对于使用Meta AI和Microsoft Designer创建图像至关重要。
此外，Google Gemini和WhiteRabbitNeo提供商也需要Cookie。
从Bing，确保您有"\_U" Cookie，从Google，需要所有以"\_\_Secure-1PSID"开头的Cookie。

**您可以直接将这些Cookie传递给create函数，或在运行G4F之前使用`set_cookies`方法设置它们：**
```python
from g4f.cookies import set_cookies

set_cookies(".bing.com", {
  "_U": "cookie值"
})

set_cookies(".google.com", {
  "__Secure-1PSID": "cookie值"
})
```
---
### HAR和Cookie文件
**使用.har和Cookie文件**
您可以将`.har`和Cookie文件`.json`放在默认的`./har_and_cookies`目录中。要导出Cookie文件，请使用Chrome网上应用店提供的[EditThisCookie扩展](https://chromewebstore.google.com/detail/editthiscookie/fngmhnnpilhplaeedifhccceomclgfbg)。

**创建.har文件以捕获Cookie**
要捕获Cookie，您还可以创建`.har`文件。有关更多详情，请参阅下一节。

### 更改Cookie目录并在Python中加载Cookie文件
**您可以更改Cookie目录并在Python环境中加载Cookie文件。要设置相对于Python文件的Cookie目录，请使用以下代码：**
```python
import os.path
from g4f.cookies import set_cookies_dir, read_cookie_files

import g4f.debug
g4f.debug.logging = True

cookies_dir = os.path.join(os.path.dirname(__file__), "har_and_cookies")
set_cookies_dir(cookies_dir)
read_cookie_files(cookies_dir)
```

### 调试模式
**如果启用调试模式，您将看到类似以下的日志：**

```
读取.har文件: ./har_and_cookies/you.com.har
添加的Cookie: 10个来自.you.com
读取Cookie文件: ./har_and_cookies/google.json
添加的Cookie: 16个来自.google.com
```

#### OpenaiChat提供商的.HAR文件

##### 生成.HAR文件

**要使用OpenaiChat提供商，需要从https://chatgpt.com/获取.har文件。请按照以下步骤创建有效的.har文件：**
1. 使用您喜欢的网络浏览器导航到https://chatgpt.com/并使用您的凭据登录。
2. 在浏览器中访问开发者工具。通常可以通过右键单击页面并选择"检查"，或按F12或Ctrl+Shift+I（Mac上为Cmd+Option+I）来实现。
3. 在开发者工具打开的情况下，切换到"网络"选项卡。
4. 重新加载网站，以在网络选项卡中捕获加载过程。
5. 在聊天中发起一个可在.har文件中捕获的操作。
6. 右键单击列出的任何网络活动，选择"将所有内容保存为HAR"以导出.har文件。

##### 存储.HAR文件

- 如果您使用Docker，将导出的.har文件放在`./har_and_cookies`目录中。或者，如果您从终端使用Python，可以将其存储在当前工作目录的`./har_and_cookies`目录中。

> **注意：** 请确保安全存储.har文件，因为它可能包含敏感信息。

### 代理配置
**如果您想为提供商隐藏或更改IP地址，可以通过环境变量全局设置代理：**

**- 在macOS和Linux上：**
```bash
export G4F_PROXY="http://host:port"
```

**- 在Windows上：**
```bash
set G4F_PROXY=http://host:port
```
