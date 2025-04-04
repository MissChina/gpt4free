# G4F - 供应商和模型

本文档提供了各种AI供应商和模型的概述，包括文本生成、图像生成和视觉能力。它旨在帮助用户在多样化的AI服务环境中导航并选择最适合其需求的选项。

> **注意**: 查看我们的[认证指南](authentication.md)了解供应商的认证说明。

## 目录
  - [供应商](#供应商)
    - [无需认证](#不需要认证的供应商)
    - [HuggingFace](#huggingface供应商)
    - [HuggingSpace](#huggingspace供应商)
    - [本地](#本地供应商)
    - [MiniMax](#minimax供应商)
    - [需要认证](#需要认证的供应商)
  - [模型](#模型)
    - [文本生成模型](#文本生成模型)
    - [图像生成模型](#图像生成模型)
  - [结论和使用提示](#结论和使用提示)

---

## 供应商

### 不需要认证的供应商
| 网站 | API凭据 | 供应商 | 文本生成 | 图像生成 | 音频生成 | 视觉(图片上传) | 状态 |
|----------|-------------|--------------|---------------|--------|--------|------|------|
|[playground.allenai.org](https://playground.allenai.org)|无需认证|`g4f.Provider.AllenAI`|`tulu-3-405b, olmo-2-13b, tulu-3-1-8b, tulu-3-70b, olmoe-0125`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[ai-arta.com](https://ai-arta.com)|无需认证|`g4f.Provider.ARTA`|❌|✔ _**(17+)**_|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[blackbox.ai](https://www.blackbox.ai)|无需认证|`g4f.Provider.Blackbox`|`blackboxai, blackboxai-pro, gpt-4o-mini, deepseek-chat, deepseek-v3, deepseek-r1, gpt-4o, o1, o3-mini, claude-3.7-sonnet` _**(40+)**_|`flux`|❌|`blackboxai, gpt-4o, o1, o3-mini, deepseek-v3` _**(7+)**_|![](https://img.shields.io/badge/Active-brightgreen)|
|[chatglm.cn](https://chatglm.cn)|无需认证|`g4f.Provider.ChatGLM`|`glm-4`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[chatgpt.com](https://chatgpt.com)|无需认证|`g4f.Provider.ChatGpt`|✔ _**(7+)**_|❌|❌|❌|![Error](https://img.shields.io/badge/HTTPError-f48d37)|
|[chatgpt.es](https://chatgpt.es)|无需认证|`g4f.Provider.ChatGptEs`|`gpt-4, gpt-4o, gpt-4o-mini`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[playground.ai.cloudflare.com](https://playground.ai.cloudflare.com)|[自动cookies](https://playground.ai.cloudflare.com)|`g4f.Provider.Cloudflare`|`llama-2-7b, llama-3-8b, llama-3.1-8b, llama-3.2-1b, qwen-1.5-7b`|❌|❌|❌|![Error](https://img.shields.io/badge/Active-brightgreen)|
|[copilot.microsoft.com](https://copilot.microsoft.com)|可选API密钥|`g4f.Provider.Copilot`|`gpt-4, o1`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[duckduckgo.com/aichat](https://duckduckgo.com/aichat)|无需认证|`g4f.Provider.DDG`|`gpt-4, gpt-4o-mini, llama-3.3-70b, claude-3-haiku, o3-mini, mixtral-small-24b`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[deepinfra.com/chat](https://deepinfra.com/chat)|无需认证|`g4f.Provider.DeepInfraChat`|`llama-3.1-8b, llama-3.2-90b, llama-3.3-70b, deepseek-v3, mixtral-small-24b, deepseek-r1, phi-4, wizardlm-2-8x22b, qwen-2.5-72b, yi-34b, qwen-2-72b, dolphin-2.6, dolphin-2.9, dbrx-instruct, airoboros-70b, lzlv-70b, wizardlm-2-7b, mixtral-8x22b, minicpm-2.5`|❌|❌|`llama-3.2-90b, minicpm-2.5`|![](https://img.shields.io/badge/Active-brightgreen)|
|[dynaspark.onrender.com](https://dynaspark.onrender.com)|无需认证|`g4f.Provider.Dynaspark`|`gemini-1.5-flash, gemini-2.0-flash`|❌|❌|`gemini-1.5-flash, gemini-2.0-flash`|![](https://img.shields.io/badge/Active-brightgreen)|
|[chat10.free2gpt.xyz](https://chat10.free2gpt.xyz)|无需认证|`g4f.Provider.Free2GPT`|`gemini-1.5-pro, gemini-1.5-flash`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[freegptsnav.aifree.site](https://freegptsnav.aifree.site)|无需认证|`g4f.Provider.FreeGpt`|`gemini-1.5-pro, gemini-1.5-flash`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[app.giz.ai/assistant](https://app.giz.ai/assistant)|无需认证|`g4f.Provider.GizAI`|`gemini-1.5-flash`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[glider.so](https://glider.so)|无需认证|`g4f.Provider.Glider`|`llama-3.1-70b, llama-3.1-8b, llama-3.2-3b, deepseek-r1`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[goabror.uz](https://goabror.uz)|无需认证|`g4f.Provider.Goabror`|`gpt-4`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[hailuo.ai](https://www.hailuo.ai)|无需认证|`g4f.Provider.HailuoAI`|`MiniMax` _**(1+)**_|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[editor.imagelabs.net](editor.imagelabs.net)|无需认证|`g4f.Provider.ImageLabs`|❌|`sdxl-turbo`|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[huggingface.co/spaces](https://huggingface.co/spaces)|可选API密钥|`g4f.Provider.HuggingSpace`|`qvq-72b, qwen-2-72b, command-r, command-r-plus, command-r7b, command-a`|`flux-dev, flux-schnell, sd-3.5`|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[jmuz.me](https://jmuz.me)|可选API密钥|`g4f.Provider.Jmuz`|`claude-3-haiku, claude-3-opus, claude-3.5-sonnet, deepseek-r1, deepseek-chat, gemini-exp, gemini-1.5-flash, gemini-1.5-pro, gemini-2.0-flash-thinking, gpt-4, gpt-4o, gpt-4o-mini, llama-3-70b, llama-3-8b, llama-3.1-405b, llama-3.1-70b, llama-3.1-8b, llama-3.2-11b, llama-3.2-90b, llama-3.3-70b, mixtral-8x7b, qwen-2.5-72b, qwen-2.5-coder-32b, qwq-32b, wizardlm-2-8x22b`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[lambda.chat](https://lambda.chat)|无需认证|`g4f.Provider.LambdaChat`|`deepseek-v3, deepseek-r1, hermes-3, nemotron-70b, llama-3.3-70b`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[liaobots.work](https://liaobots.work)|[自动cookies](https://liaobots.work)|`g4f.Provider.Liaobots`|`claude-3.5-sonnet, claude-3.7-sonnet, claude-3.7-sonnet-thinking, claude-3-opus, claude-3-sonnet, deepseek-r1, deepseek-v3, gemini-2.0-flash, gemini-2.0-flash-thinking, gemini-2.0-pro, gpt-4, gpt-4o, gpt-4o-mini, grok-3, grok-3-r1, o3-mini`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[oi-vscode-server.onrender.com](https://oi-vscode-server.onrender.com)|无需认证|`g4f.Provider.OIVSCode`|`gpt-4o-mini, deepseek-v3`|❌|❌|`gpt-4o-mini`|![](https://img.shields.io/badge/Active-brightgreen)|
|[labs.perplexity.ai](https://labs.perplexity.ai)|无需认证|`g4f.Provider.PerplexityLabs`|`sonar, sonar-pro, sonar-reasoning, sonar-reasoning-pro`|❌|❌|❌|![Error](https://img.shields.io/badge/Active-brightgreen)|
|[pi.ai/talk](https://pi.ai/talk)|[手动cookies](https://pi.ai/talk)|`g4f.Provider.Pi`|`pi`|❌|❌|❌|![Error](https://img.shields.io/badge/Active-brightgreen)|
|[pizzagpt.it](https://www.pizzagpt.it)|无需认证|`g4f.Provider.Pizzagpt`|`gpt-4o-mini`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[pollinations.ai](https://pollinations.ai)|无需认证|`g4f.Provider.PollinationsAI`|`gpt-4o-mini, gpt-4o, o1-mini, qwen-2.5-coder-32b, llama-3.3-70b, mistral-nemo, llama-3.1-8b, deepseek-r1, phi-4` _**(9+)**_|`flux, flux-pro, flux-dev, flux-schnell, dall-e-3, sdxl-turbo`|`gpt-4o-audio`|`gpt-4o, gpt-4o-mini, o1-mini, o3-mini`|![](https://img.shields.io/badge/Active-brightgreen)|
|[pollinations.ai](https://pollinations.ai)|无需认证|`g4f.Provider.PollinationsImage`|❌|`flux, flux-pro, flux-dev, flux-schnell, dall-e-3, sdxl-turbo`|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[teach-anything.com](https://www.teach-anything.com)|无需认证|`g4f.Provider.TeachAnything`|`gemini-1.5-pro, gemini-1.5-flash`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[chat.typegpt.net](https://chat.typegpt.net)|无需认证|`g4f.Provider.TypeGPT`|`gpt-3.5-turbo, o3-mini, deepseek-r1, deepseek-v3, evil, o1`|❌|❌|`gpt-3.5-turbo, o3-mini`|![](https://img.shields.io/badge/Active-brightgreen)|
|[you.com](https://you.com)|[手动cookies](https://you.com)|`g4f.Provider.You`|✔|✔|❌|✔|![](https://img.shields.io/badge/Active-brightgreen)|
|[websim.ai](https://websim.ai)|无需认证|`g4f.Provider.Websim`|`gemini-1.5-pro, gemini-1.5-flash`|`flux`|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[chat9.yqcloud.top](https://chat9.yqcloud.top)|无需认证|`g4f.Provider.Yqcloud`|`gpt-4`|✔|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|

---

### HuggingFace供应商
| 网站 | API凭据 | 供应商 | 文本生成 | 图像生成 | 音频生成 | 视觉(图片上传) | 状态 |
|----------|-------------|--------------|---------------|--------|--------|------|------|
|[huggingface.co/chat](https://huggingface.co/chat)|[手动cookies](https://huggingface.co/chat)|`g4f.Provider.HuggingChat`|`qwen-2.5-72b, llama-3.3-70b, command-r-plus, deepseek-r1, qwq-32b, nemotron-70b, llama-3.2-11b, mistral-nemo, phi-3.5-mini`|`flux-dev, flux-schnell`|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[huggingface.co/chat](https://huggingface.co/chat)|[API密钥 / Cookies](https://huggingface.co/settings/tokens)|`g4f.Provider.HuggingFace`|✔ _**(47+)**_|✔ _**(9+)**_|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[api-inference.huggingface.co](https://api-inference.huggingface.co)|[获取API密钥](https://huggingface.co/settings/tokens)|`g4f.Provider.HuggingFaceAPI`|✔ _**(9+)**_|✔ _**(2+)**_|❌|✔ _**(1+)**_|![](https://img.shields.io/badge/Active-brightgreen)|

---

### HuggingSpace供应商
| 网站 | API凭据 | 供应商 | 文本生成 | 图像生成 | 音频生成 | 视觉(图片上传) | 状态 |
|----------|-------------|--------------|---------------|--------|--------|------|------|
|[black-forest-labs-flux-1-dev.hf.space](https://black-forest-labs-flux-1-dev.hf.space)|[获取API密钥](https://huggingface.co/settings/tokens)|`g4f.Provider.BlackForestLabs_Flux1Dev`|❌|`flux, flux-dev`|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[black-forest-labs-flux-1-schnell.hf.space](https://black-forest-labs-flux-1-schnell.hf.space)|[获取API密钥](https://huggingface.co/settings/tokens)|`g4f.Provider.BlackForestLabs_Flux1Schnell`|❌|`flux, flux-schnell`|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[cohereforai-c4ai-command.hf.space](https://cohereforai-c4ai-command.hf.space)|[获取API密钥](https://huggingface.co/settings/tokens)|`g4f.Provider.CohereForAI_C4AI_Command`|`command-r, command-r-plus, command-r7b`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[huggingface.co/spaces/deepseek-ai/Janus-Pro-7B](https://huggingface.co/spaces/deepseek-ai/Janus-Pro-7B)|[获取API密钥](https://huggingface.co/settings/tokens)|`g4f.Provider.DeepseekAI_Janus_Pro_7b`|✔|✔|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[roxky-flux-1-dev.hf.space](https://roxky-flux-1-dev.hf.space)|[获取API密钥](https://huggingface.co/settings/tokens)|`g4f.Provider.G4F`|✔ _**(1+)**_|✔ _**(4+)**_|❌|✔ _**(1+)**_|![](https://img.shields.io/badge/Active-brightgreen)|
|[microsoft-phi-4-multimodal.hf.space](https://microsoft-phi-4-multimodal.hf.space)|[获取API密钥](https://huggingface.co/settings/tokens)|`g4f.Provider.Microsoft_Phi_4`|`phi-4`|❌|❌|`phi-4`|![](https://img.shields.io/badge/Active-brightgreen)|
|[qwen-qvq-72b-preview.hf.space](https://qwen-qvq-72b-preview.hf.space)|[获取API密钥](https://huggingface.co/settings/tokens)|`g4f.Provider.Qwen_QVQ_72B`|`qvq-72b`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[qwen-qwen2-5.hf.space](https://qwen-qwen2-5.hf.space)|[获取API密钥](https://huggingface.co/settings/tokens)|`g4f.Provider.Qwen_Qwen_2_5`|`qwen-2.5`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[qwen-qwen2-5-1m-demo.hf.space](https://qwen-qwen2-5-1m-demo.hf.space)|[获取API密钥](https://huggingface.co/settings/tokens)|`g4f.Provider.Qwen_Qwen_2_5M`|`qwen-2.5-1m`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[qwen-qwen2-5-max-demo.hf.space](https://qwen-qwen2-5-max-demo.hf.space)|[获取API密钥](https://huggingface.co/settings/tokens)|`g4f.Provider.Qwen_Qwen_2_5_Max`|`qwen-2-5-max`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[qwen-qwen2-72b-instruct.hf.space](https://qwen-qwen2-72b-instruct.hf.space)|[获取API密钥](https://huggingface.co/settings/tokens)|`g4f.Provider.Qwen_Qwen_2_72B`|`qwen-2-72b`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[stabilityai-stable-diffusion-3-5-large.hf.space](https://stabilityai-stable-diffusion-3-5-large.hf.space)|[获取API密钥](https://huggingface.co/settings/tokens)|`g4f.Provider.StabilityAI_SD35Large`|❌|`sd-3.5`|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[voodoohop-flux-1-schnell.hf.space](https://voodoohop-flux-1-schnell.hf.space)|[获取API密钥](https://huggingface.co/settings/tokens)|`g4f.Provider.Voodoohop_Flux1Schnell`|❌|`flux, flux-schnell`|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|

### 本地供应商
| 网站 | API凭据 | 供应商 | 文本生成 | 图像生成 | 音频生成 | 视觉(图片上传) | 状态 |
|----------|-------------|--------------|---------------|--------|--------|------|------|
|[]( )|无需认证|`g4f.Provider.Local`|✔|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[ollama.com](https://ollama.com)|无需认证|`g4f.Provider.Ollama`|✔|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|

---

### MiniMax供应商
| 网站 | API凭据 | 供应商 | 文本生成 | 图像生成 | 音频生成 | 视觉(图片上传) | 状态 |
|----------|-------------|--------------|---------------|--------|--------|------|------|
|[hailuo.ai/chat](https://www.hailuo.ai/chat)|[获取API密钥](https://intl.minimaxi.com/user-center/basic-information/interface-key)|`g4f.Provider.MiniMax`|`MiniMax`  _**(1+)**_|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|

---

### 需要认证的供应商
| 网站 | API凭据 | 供应商 | 文本生成 | 图像生成 | 音频生成 | 视觉(图片上传) | 状态 |
|----------|-------------|--------------|---------------|--------|--------|------|------|
|[console.anthropic.com](https://console.anthropic.com)|[获取API密钥](https://console.anthropic.com/settings/keys)|`g4f.Provider.Anthropic`|✔ _**(8+)**_|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[bing.com/images/create](https://www.bing.com/images/create)|[手动cookies](https://www.bing.com)|`g4f.Provider.BingCreateImages`|❌|`dall-e-3`|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[cablyai.com/chat](https://cablyai.com/chat)|[获取API密钥](https://cablyai.com)|`g4f.Provider.CablyAI`|✔|✔|❌|✔|![](https://img.shields.io/badge/Active-brightgreen)|
|[inference.cerebras.ai](https://inference.cerebras.ai/)|[获取API密钥](https://cloud.cerebras.ai)|`g4f.Provider.Cerebras`|✔ _**(3+)**_|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[copilot.microsoft.com](https://copilot.microsoft.com)|[手动cookies](https://copilot.microsoft.com)|`g4f.Provider.CopilotAccount`|✔ _**(1+)**_|✔ _**(1+)**_|❌|✔ _**(1+)**_|![](https://img.shields.io/badge/Active-brightgreen)|
|[deepinfra.com](https://deepinfra.com)|[获取API密钥](https://deepinfra.com/dash/api_keys)|`g4f.Provider.DeepInfra`|✔ _**(17+)**_|✔ _**(6+)**_|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[platform.deepseek.com](https://platform.deepseek.com)|[获取API密钥](https://platform.deepseek.com/api_keys)|`g4f.Provider.DeepSeek`|✔ _**(1+)**_|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[gemini.google.com](https://gemini.google.com)|[手动cookies](https://gemini.google.com)|`g4f.Provider.Gemini`|`gemini-2.0`|`gemini-2.0`|❌|`gemini-2.0`|![](https://img.shields.io/badge/Active-brightgreen)|
|[ai.google.dev](https://ai.google.dev)|[获取API密钥](https://aistudio.google.com/u/0/apikey)|`g4f.Provider.GeminiPro`|`gemini-1.5-flash, gemini-1.5-pro, gemini-2.0-flash`|❌|❌|`gemini-1.5-pro`|![](https://img.shields.io/badge/Active-brightgreen)|
|[developers.sber.ru/gigachat](https://developers.sber.ru/gigachat)|[手动cookies](https://developers.sber.ru/gigachat)|`g4f.Provider.GigaChat`|✔ _**(3+)**_|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[github.com/copilot](https://github.com/copilot)|[手动cookies](https://github.com/copilot)|`g4f.Provider.GithubCopilot`|✔ _**(4+)**_|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[glhf.chat](https://glhf.chat)|[获取API密钥](https://glhf.chat/user-settings/api)|`g4f.Provider.GlhfChat`|✔ _**(22+)**_|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[console.groq.com/playground](https://console.groq.com/playground)|[获取API密钥](https://console.groq.com/keys)|`g4f.Provider.Groq`|✔ _**(18+)**_|❌|❌|✔|![](https://img.shields.io/badge/Active-brightgreen)|
|[meta.ai](https://www.meta.ai)|[手动cookies](https://www.meta.ai)|`g4f.Provider.MetaAI`|`meta-ai`|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[meta.ai](https://www.meta.ai)|[手动cookies](https://www.meta.ai)|`g4f.Provider.MetaAIAccount`|❌|`meta-ai`|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[designer.microsoft.com](https://designer.microsoft.com)|[手动cookies](https://designer.microsoft.com)|`g4f.Provider.MicrosoftDesigner`|❌|`dall-e-3`|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[platform.openai.com](https://platform.openai.com)|[获取API密钥](https://platform.openai.com/settings/organization/api-keys)|`g4f.Provider.OpenaiAPI`|✔|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[chatgpt.com](https://chatgpt.com)|[手动cookies](https://chatgpt.com)|`g4f.Provider.OpenaiChat`|`gpt-4o, gpt-4o-mini, gpt-4` _**(8+)**_|✔ _**(1)**_|❌|✔ _**(8+)**_|![](https://img.shields.io/badge/Active-brightgreen)|
|[perplexity.ai](https://www.perplexity.ai)|[获取API密钥](https://www.perplexity.ai/settings/api)|`g4f.Provider.PerplexityApi`|✔ _**(6+)**_|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[chat.reka.ai](https://chat.reka.ai)|[手动cookies](https://chat.reka.ai)|`g4f.Provider.Reka`|`reka-core`|✔|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[replicate.com](https://replicate.com)|[获取API密钥](https://replicate.com/account/api-tokens)|`g4f.Provider.Replicate`|✔ _**(1+)**_|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[beta.theb.ai](https://beta.theb.ai)|[获取API密钥](https://beta.theb.ai)|`g4f.Provider.ThebApi`|✔ _**(21+)**_|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[whiterabbitneo.com](https://www.whiterabbitneo.com)|[手动cookies](https://www.whiterabbitneo.com)|`g4f.Provider.WhiteRabbitNeo`|✔|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|
|[console.x.ai](https://console.x.ai)|[获取API密钥](https://console.x.ai)|`g4f.Provider.xAI`|✔|❌|❌|❌|![](https://img.shields.io/badge/Active-brightgreen)|

---

## 模型

### 文本生成模型
| 模型 | 基础供应商 | 供应商 | 网站 |
|-------|---------------|-----------|---------|
|gpt-3.5-turbo|OpenAI|1+ 供应商|[platform.openai.com](https://platform.openai.com/docs/engines/gpt-3.5-turbo)|
|gpt-4|OpenAI|9+ 供应商|[platform.openai.com](https://platform.openai.com/docs/models/gpt-4-turbo-and-gpt-4)|
|gpt-4o|OpenAI|6+ 供应商|[platform.openai.com](https://platform.openai.com/docs/models/gpt-4o)|
|gpt-4o-mini|OpenAI|9+ 供应商|[platform.openai.com](https://platform.openai.com/docs/models/gpt-4o-mini)|
|o1|OpenAI|4+ 供应商|[openai.com](https://openai.com/index/introducing-openai-o1-preview/)|
|o1-mini|OpenAI|1+ 供应商|[openai.com](https://openai.com/index/openai-o1-mini-advancing-cost-efficient-reasoning/)|
|o3-mini|OpenAI|4+ 供应商|[openai.com](https://openai.com/index/openai-o3-mini/)|
|gigachat|GigaChat|1+ 供应商|[developers.sber.ru/gigachat](https://developers.sber.ru/gigachat)|
|meta-ai|Meta|1+ 供应商|[ai.meta.com](https://ai.meta.com/)|
|llama-2-7b|Meta Llama|1+ 供应商|[huggingface.co](https://huggingface.co/meta-llama/Llama-2-7b)|
|llama-3-8b|Meta Llama|2+ 供应商|[ai.meta.com](https://ai.meta.com/blog/meta-llama-3/)|
|llama-3-70b|Meta Llama|1+ 供应商|[huggingface.co](https://huggingface.co/meta-llama/Meta-Llama-3-70B)|
|llama-3.1-8b|Meta Llama|6+ 供应商|[ai.meta.com](https://ai.meta.com/blog/meta-llama-3-1/)|
|llama-3.1-70b|Meta Llama|3+ 供应商|[ai.meta.com](https://ai.meta.com/blog/meta-llama-3-1/)|
|llama-3.1-405b|Meta Llama|2+ 供应商|[huggingface.co](https://huggingface.co/meta-llama/Llama-3.1-405B)|
|llama-3.2-1b|Meta Llama|1+ 供应商|[huggingface.co](https://huggingface.co/meta-llama/Llama-3.2-1B)|
|llama-3.2-3b|Meta Llama|1+ 供应商|[huggingface.co](https://huggingface.co/meta-llama/Llama-3.2-3B)|
|llama-3.2-11b|Meta Llama|3+ 供应商|[ai.meta.com](https://ai.meta.com/blog/llama-3-2-connect-2024-vision-edge-mobile-devices/)|
|llama-3.2-90b|Meta Llama|2+ 供应商|[huggingface.co](https://huggingface.co/meta-llama/Llama-3.2-90B-Vision)|
|llama-3.3-70b|Meta Llama|7+ 供应商|[ai.meta.com](https://ai.meta.com/blog/llama-3-3/)|
|mixtral-8x7b|Mistral|1+ 供应商|[mistral.ai](https://mistral.ai/news/mixtral-of-experts/)|
|mixtral-8x22b|Mistral|1+ 供应商|[huggingface.co](https://huggingface.co/mistralai/Mixtral-8x22B-Instruct-v0.1)|
|mistral-nemo|Mistral|3+ 供应商|[huggingface.co](https://huggingface.co/mistralai/Mistral-Nemo-Instruct-2407)|
|mixtral-small-24b|Mistral|2+ 供应商|[huggingface.co](https://huggingface.co/mistralai/Mistral-Small-24B-Instruct-2501)|
|hermes-3|NousResearch|1+ 供应商|[huggingface.co](https://huggingface.co/NousResearch/Hermes-3-Llama-3.1-405B-FP8)|
|phi-3.5-mini|Microsoft|1+ 供应商|[huggingface.co](https://huggingface.co/microsoft/Phi-3.5-mini-instruct)|
|phi-4|Microsoft|3+ 供应商|[techcommunity.microsoft.com](https://techcommunity.microsoft.com/blog/aiplatformblog/introducing-phi-4-microsoft%E2%80%99s-newest-small-language-model-specializing-in-comple/4357090)|
|wizardlm-2-7b|Microsoft|1+ 供应商|[wizardlm.github.io](https://wizardlm.github.io/WizardLM2/)|
|wizardlm-2-8x22b|Microsoft|2+ 供应商|[wizardlm.github.io](https://wizardlm.github.io/WizardLM2/)|
|gemini-exp|Google DeepMind|1+ 供应商|[blog.google](https://blog.google/feed/gemini-exp-1206/)|
|gemini-1.5-flash|Google DeepMind|7+ 供应商|[deepmind.google](https://deepmind.google/technologies/gemini/flash/)|
|gemini-1.5-pro|Google DeepMind|6+ 供应商|[deepmind.google](https://deepmind.google/technologies/gemini/pro/)|
|gemini-2.0|Google DeepMind|1+ 供应商|[deepmind.google](http://deepmind.google/technologies/gemini/)|
|gemini-2.0-flash|Google DeepMind|3+ 供应商|[deepmind.google](https://deepmind.google/technologies/gemini/flash/)|
|gemini-2.0-flash-thinking|Google DeepMind|1+ 供应商|[ai.google.dev](https://ai.google.dev/gemini-api/docs/thinking-mode)|
|gemini-2.0-pro|Google DeepMind|1+ 供应商|[deepmind.google](https://deepmind.google/technologies/gemini/flash-thinking/)|
|claude-3-haiku|Anthropic|2+ 供应商|[anthropic.com](https://www.anthropic.com/news/claude-3-haiku)|
|claude-3-sonnet|Anthropic|1+ 供应商|[anthropic.com](https://www.anthropic.com/news/claude-3-family)|
|claude-3-opus|Anthropic|2+ 供应商|[anthropic.com](https://www.anthropic.com/news/claude-3-family)|
|claude-3.5-sonnet|Anthropic|2+ 供应商|[anthropic.com](https://www.anthropic.com/news/claude-3-5-sonnet)|
|claude-3.7-sonnet|Anthropic|2+ 供应商|[anthropic.com](https://www.anthropic.com/claude/sonnet)|
|claude-3.7-sonnet-thinking|Anthropic|1+ 供应商|[anthropic.com](https://www.anthropic.com/claude/sonnet)|
|reka-core|Reka AI|1+ 供应商|[reka.ai](https://www.reka.ai/ourmodels)|
|blackboxai|Blackbox AI|1+ 供应商|[docs.blackbox.chat](https://docs.blackbox.chat/blackbox-ai-1)|
|blackboxai-pro|Blackbox AI|1+ 供应商|[docs.blackbox.chat](https://docs.blackbox.chat/blackbox-ai-1)|
|command-r|CohereForAI|1+ 供应商|[docs.cohere.com](https://docs.cohere.com/docs/command-r-plus)|
|command-r-plus|CohereForAI|2+ 供应商|[docs.cohere.com](https://docs.cohere.com/docs/command-r-plus)|
|command-r7b|CohereForAI|1+ 供应商|[huggingface.co](https://huggingface.co/CohereForAI/c4ai-command-r7b-12-2024)|
|command-a|CohereForAI|1+ 供应商|[docs.cohere.com](https://docs.cohere.com/v2/docs/command-a)|
|qwen-1.5-7b|Qwen|1+ 供应商|[huggingface.co](https://huggingface.co/Qwen/Qwen1.5-7B)|
|qwen-2-72b|Qwen|2+ 供应商|[huggingface.co](https://huggingface.co/Qwen/Qwen2-72B)|
|qwen-2-vl-7b|Qwen|1+ 供应商|[huggingface.co](https://huggingface.co/Qwen/Qwen2-VL-7B)|
|qwen-2.5-72b|Qwen|1+ 供应商|[huggingface.co](https://huggingface.co/Qwen/Qwen2.5-72B-Instruct)|
|qwen-2.5-coder-32b|Qwen|3+ 供应商|[huggingface.co](https://huggingface.co/Qwen/Qwen2.5-Coder-32B)|
|qwen-2.5-1m|Qwen|1+ 供应商|[huggingface.co](https://huggingface.co/Qwen/Qwen2.5-1M-Demo)|
|qwen-2-5-max|Qwen|1+ 供应商|[qwen-ai.com](https://www.qwen-ai.com/2-5-max/)|
|qwq-32b|Qwen|2+ 供应商|[huggingface.co](https://huggingface.co/Qwen/QwQ-32B-Preview)|
|qvq-72b|Qwen|1+ 供应商|[huggingface.co](https://huggingface.co/Qwen/QVQ-72B-Preview)|
|pi|Inflection|1+ 供应商|[inflection.ai](https://inflection.ai/blog/inflection-2-5)|
|deepseek-chat|DeepSeek|2+ 供应商|[huggingface.co](https://huggingface.co/deepseek-ai/deepseek-llm-67b-chat)|
|deepseek-v3|DeepSeek|5+ 供应商|[api-docs.deepseek.com](https://api-docs.deepseek.com/news/news250120)|
|deepseek-r1|DeepSeek|10+ 供应商|[api-docs.deepseek.com](https://api-docs.deepseek.com/news/news250120)|
|janus-pro-7b|DeepSeek|2+ 供应商|[api-docs.deepseek.com](https://api-docs.deepseek.com/docs/janus-pro-7b)|
|grok-3|x.ai|1+ 供应商|[x.ai](https://x.ai/blog/grok-3)|
|grok-3-r1|x.ai|1+ 供应商|[x.ai](https://x.ai/blog/grok-3)|
|sonar|Perplexity AI|1+ 供应商|[sonar.perplexity.ai](https://sonar.perplexity.ai/)|
|sonar-pro|Perplexity AI|1+ 供应商|[sonar.perplexity.ai](https://sonar.perplexity.ai/)|
|sonar-reasoning|Perplexity AI|1+ 供应商|[sonar.perplexity.ai](https://sonar.perplexity.ai/)|
|sonar-reasoning-pro|Perplexity AI|1+ 供应商|[sonar.perplexity.ai](https://sonar.perplexity.ai/)|
|r1-1776|Perplexity AI|1+ 供应商|[perplexity.ai](https://www.perplexity.ai/hub/blog/open-sourcing-r1-1776)|
|nemotron-70b|Nvidia|3+ 供应商|[build.nvidia.com](https://build.nvidia.com/nvidia/llama-3_1-nemotron-70b-instruct)|
|dbrx-instruct|Databricks|1+ 供应商|[huggingface.co](https://huggingface.co/databricks/dbrx-instruct)|
|glm-4|THUDM|1+ 供应商|[github.com/THUDM](https://github.com/THUDM/GLM-4)|
|mini_max|MiniMax|1+ 供应商|[hailuo.ai](https://www.hailuo.ai/)|
|yi-34b|01-ai|1+ 供应商|[huggingface.co](https://huggingface.co/01-ai/Yi-34B-Chat)|
|dolphin-2.6|Cognitive Computations|1+ 供应商|[huggingface.co](https://huggingface.co/cognitivecomputations/dolphin-2.6-mixtral-8x7b)|
|dolphin-2.9|Cognitive Computations|1+ 供应商|[huggingface.co](https://huggingface.co/cognitivecomputations/dolphin-2.9.1-llama-3-70b)|
|airoboros-70b|DeepInfra|1+ 供应商|[huggingface.co](https://huggingface.co/cognitivecomputations/dolphin-2.9.1-llama-3-70b)|
|lzlv-70b|Lizpreciatior|1+ 供应商|[huggingface.co](https://huggingface.co/cognitivecomputations/dolphin-2.9.1-llama-3-70b)|
|minicpm-2.5|OpenBMB|1+ 供应商|[huggingface.co](https://huggingface.co/openbmb/MiniCPM-Llama3-V-2_5)|
|tulu-3-405b|Ai2|1+ 供应商|[allenai.org](https://allenai.org/documentation)|
|olmo-2-13b|Ai2|1+ 供应商|[allenai.org](https://allenai.org/documentation)|
|tulu-3-1-8b|Ai2|1+ 供应商|[allenai.org](https://allenai.org/documentation)|
|tulu-3-70b|Ai2|1+ 供应商|[allenai.org](https://allenai.org/documentation)|
|olmoe-0125|Ai2|1+ 供应商|[allenai.org](https://allenai.org/documentation)|
|lfm-40b|Liquid AI|1+ 供应商|[liquid.ai](https://www.liquid.ai/liquid-foundation-models)|
|evil|Evil Mode - Experimental|2+ 供应商|[]( )|

---

### 图像生成模型
| 模型 | 基础供应商 | 供应商 | 网站 |
|-------|---------------|-----------|---------|
|sdxl-turbo|Stability AI|2+ 供应商|[huggingface.co](https://huggingface.co/stabilityai/sdxl-turbo)|
|sd-3.5|Stability AI|1+ 供应商|[huggingface.co](https://huggingface.co/stabilityai/stable-diffusion-3.5-large)|
|flux|Black Forest Labs|4+ 供应商|[github.com/black-forest-labs/flux](https://github.com/black-forest-labs/flux)|
|flux-pro|Black Forest Labs|1+ 供应商|[huggingface.co](https://huggingface.co/enhanceaiteam/FLUX.1-Pro)|
|flux-dev|Black Forest Labs|4+ 供应商|[huggingface.co](https://huggingface.co/black-forest-labs/FLUX.1-dev)|
|flux-schnell|Black Forest Labs|4+ 供应商|[huggingface.co](https://huggingface.co/black-forest-labs/FLUX.1-schnell)|
|dall-e-3|OpenAI|5+ 供应商|[openai.com](https://openai.com/index/dall-e/)|
|midjourney|Midjourney|1+ 供应商|[docs.midjourney.com](https://docs.midjourney.com/docs/model-versions)|

---

### 音频生成模型
| 模型 | 基础供应商 | 供应商 | 网站 |
|-------|---------------|-----------|---------|
|gpt-4o-audio|Stability AI|1+ 供应商|[platform.openai.com](https://platform.openai.com/docs/models/gpt-4o-audio)|


## 结论和使用提示
本文档提供了各种AI供应商和模型的全面概述，涵盖文本生成、图像生成和视觉任务。**在选择供应商或模型时，请考虑以下因素:**
   1. **可用性**: 检查供应商的状态，确保其当前处于活动状态并可访问。
   2. **模型能力**: 不同的模型在不同任务上表现出色。选择最适合您特定需求的模型，无论是文本生成、图像创建还是视觉相关任务。
   3. **认证**: 一些供应商需要认证，而另一些则不需要。在为您的项目选择供应商时，请考虑这一点。
   4. **视觉模型**: 对于需要图像理解或多模态交互的任务，请寻找提供视觉模型的供应商。

请记住，AI领域不断涌现和发展的新模型和供应商，请保持更新。

---

[返回首页](/)
