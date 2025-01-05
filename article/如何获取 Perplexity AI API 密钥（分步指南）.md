
# 如何获取 Perplexity AI API 密钥（分步指南）

Perplexity AI 是一款结合搜索引擎和聊天机器人功能的人工智能工具，以卓越的自然语言处理能力和广泛的应用场景吸引了众多开发者。通过 Perplexity AI API，开发者能够为项目或应用注入全新活力。本文将为您提供详细的分步指南，帮助您轻松获取 API 密钥并集成到您的应用中。

---

## Perplexity AI 的特点和优势

Perplexity AI 是由 Andy Konwinski 等人创立的智能工具，专注于信息搜索与整合服务。通过其 API，开发者能够：
- **提升用户体验**：快速响应用户查询，提供准确答案。
- **增强产品功能**：实现自然语言交互、知识检索等高级功能。
- **广泛应用场景**：适用于聊天机器人、数据分析、内容生成等领域。

---

## 1. 注册并登录 Perplexity AI

### 第一步：访问 Perplexity AI 官网
打开 Perplexity AI 的官方网站，点击右上角注册按钮，完成账号创建。建议使用常用邮箱，以便后续接收 API 密钥信息。

![登录注册界面](https://cdn.explinks.com/wp-content/uploads/2024/11/image-58-1024x486.png)

---

## 2. 获取 API 密钥

完成账号注册后，按照以下步骤获取 API 密钥。

### 第二步：添加支付方式
- 在账户设置中，绑定有效的信用卡信息。请放心，此步骤不会扣款，仅用于存储支付信息以便未来使用。
- 支持多种支付方式，建议优先选择国际信用卡。

![支付方式设置](https://cdn.explinks.com/wp-content/uploads/2024/11/image-62-1024x616.png)

### 第三步：生成 API 密钥
1. 进入 API 控制面板。
2. 点击“生成 API 密钥”按钮。
3. 保存生成的密钥，确保妥善保管。

![生成 API 密钥](https://cdn.explinks.com/wp-content/uploads/2024/11/image-64-1013x1024.png)

> **提示**：API 密钥长期有效，除非您手动刷新或删除。

---

## 3. API 请求示例

以下代码展示了如何通过 Perplexity AI API 实现自然语言交互。

```python
from openai import OpenAI

YOUR_API_KEY = "INSERT_API_KEY_HERE"

messages = [
    {
        "role": "system",
        "content": (
            "You are an artificial intelligence assistant, "
            "engage in a helpful, detailed, and polite conversation with the user."
        ),
    },
    {
        "role": "user",
        "content": "How many stars are in the universe?",
    },
]

client = OpenAI(api_key=YOUR_API_KEY, base_url="https://api.perplexity.ai")

# Chat completion without streaming
response = client.chat.completions.create(
    model="llama-3.1-sonar-large-128k-online",
    messages=messages,
)
print(response)

# Chat completion with streaming
response_stream = client.chat.completions.create(
    model="llama-3.1-sonar-large-128k-online",
    messages=messages,
    stream=True,
)
for response in response_stream:
    print(response)
```

---

## 4. PerplexityBot 爬虫服务

PerplexityBot 是 Perplexity AI 的网络爬虫，负责收集数据并将其编入搜索引擎索引中。您可以通过以下方式自定义对爬虫的访问权限。

### 禁止 PerplexityBot
在网站根目录的 `robots.txt` 文件中添加以下内容：
```plaintext
User-Agent: PerplexityBot
Disallow: /
```

### 自定义访问规则
允许爬虫访问公开区域，禁止访问私密区域：
```plaintext
User-Agent: PerplexityBot
Allow: /public/
Disallow: /private/
```

---

## **推荐**：轻松管理 API 支付方式

[WildCard | 一分钟注册，轻松订阅海外线上服务](https://bit.ly/bewildcard)

- 支持多种国际支付场景：ChatGPT、Claude、Google Play、Apple Store 等。
- 使用邀请码 **ACCPAY**，立享消费 0 手续费，减免开卡费用。
- 支持支付宝、微信支付，方便快捷。

---

## 5. 常见问题解答

### Q1: 如何解决 API 密钥授权错误？
**A**：401 错误表示 API 密钥无效或账户余额不足。请前往仪表板充值或更新密钥。

### Q2: 数据是否会用于模型训练？
**A**：Perplexity AI 仅收集使用元数据（如请求次数），用于计费和统计分析，确保用户隐私不被侵犯。

### Q3: 是否支持自动充值？
**A**：支持。当余额低于 $2 时，系统会自动充值。

### Q4: API 是否支持高并发请求？
**A**：Perplexity AI 提供企业版服务，支持更高的请求并发能力，详情请咨询技术支持。

---

## 6. 总结

本文详细介绍了获取 Perplexity AI API 密钥的完整流程，并提供了集成示例代码和常见问题解答。通过注册账户、设置支付方式、生成 API 密钥，开发者可以轻松解锁 Perplexity AI 的强大功能，并快速将其应用于各类项目中。

借助 Perplexity AI，您可以在自然语言处理领域实现更多创意和突破。赶快行动，开始探索无限可能吧！
