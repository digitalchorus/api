# Shapes API

[![image](https://github.com/user-attachments/assets/e98592ca-3b1d-4709-93c6-7e6aa0dfb84a)](https://shapes.inc/slack)


[Shapes](https://shapes.inc) are general purpose social agents. You can build for an [existing shape](https://shapes.inc/explore) from our catalogue of millions or [create](https://shapes.inc/create) your own. Shapes have rich personalities, love hanging out in groupchats, and short-term + long-term memory across platforms.

The Shapes API enables developers to connect Shapes across social platforms, games, and other applications. Shapes can meet you anywhere, from your favorite social app or a new project. You can configure a Shape to use some of 50+ models we offer for free across text, image, and voice.

## Open Source Contributions
Our API is designed with extensibility as a core principle. You can extend any Shape for tool calling, MCP, and more.

Star and contribute to this repository to receive free hosting for your integration. We will also be directing traffic from our user base to your integration.

## What is the Shapes API?
Shapes API provides a programmatic way to integrate Shapes into any application or platform. It follows the OpenAI-compatible API standard, making it easy to implement with existing libraries and SDKs.

To learn more about implementing Shapes in your app, check out our [examples repository](https://github.com/shapesinc/api).

![Features](https://img.intercomm.in/su88a4.png)

Shapes API comes with many features that you probably won’t find in general APIs. Here's a quick overview:

### Memories
Shapes API supports memory!
If you're using the API through a method linked to your Shapes Inc login (like email), Shapes will automatically reference your previous DM memories across sessions.

### Image Generation
You can generate images directly through Shapes API — just use the `!imagine` command or the relevant endpoint.

### 50+ Models
Access all trending LLMs including GPT-4.1, Claude Sonnet 3.7, Gemini 2.5 Pro, and more — all through a single API. Models can be configured in the AI Engine tab on the selected shape's dashboard.

### Voice Generation
Shapes API supports voice messages!
Configure your integration to send back audio replies using the built-in voice features.

Check out the examples in the repo to learn how to use each of these features in your integration!

## Getting Started
You will need to generate an API Key. Every API Key is tied to a specific Shape. Get yours [here](https://shapes.inc/developer)

<img width="807" alt="API Key Generation" src="https://github.com/user-attachments/assets/ead6f28a-300b-4dcf-a555-313b39656ad6" />

## Implementation Examples

### 🐍 Python

```python
import openai

shapes_client = OpenAI(
    api_key="<your-API-key>",
    base_url="https://api.shapes.inc/v1/",
)

response = shapes_client.chat.completions.create(
    model="shapesinc/<shape-username>",
    messages=[
        {"role": "user", "content": "Hello"}
    ]
)

print(response)
```

### 🌐 JavaScript

```javascript
const openai = require("openai");

const shapes_client = new OpenAI({
    apiKey: "<your-API-key>",
    baseURL: "https://api.shapes.inc/v1",
});

const response = await shapes_client.chat.completions.create({
    model: "shapesinc/<shape-username>",
    messages: [
        { role: "user", content: "Hello" }
    ]
});

console.log(response);
```

### 🔄 CURL

```bash
curl -X POST https://api.shapes.inc/v1/chat/completions \
     -H "Authorization: Bearer <your-API-key>" \
     -H "Content-Type: application/json" \
     -d '{"model": "shapesinc/<shape-username>", "messages": [{ "role": "user", "content": "Hello" }]}'
```

### Quick Setup

| Requirement | Details |
|-------------|---------|
| Base URL | `https://api.shapes.inc/v1/` |
| Model Format | `shapesinc/<shape-username>` |
| Authentication | Bearer token in Authorization header |
| Environment Variables | `SHAPESINC_API_KEY` and `SHAPESINC_SHAPE_USERNAME` |

### API Specifications

| Feature | Details |
|---------|---------|
| Endpoints | `/chat/completions` |
| Rate Limits | 5 API Keys per account (request increase [here](https://docs.google.com/forms/d/e/1FAIpQLScGLeRk6snViRPslXbbUaMDwubcBhmcJ6opq7wFvPEp-EbO3g/viewform)) |
| Headers | `X-User-Id` for user identification, `X-Channel-Id` for conversation context |
| Response Format | Standard OpenAI-compatible JSON response |

## Supported Commands

Shapes now support the following commands:
- `!reset` - Reset the Shape's long-term memory
- `!sleep` - Generate a long-term on demand 
- `!dashboard` - Access the Shape's dedicated dashboard for configuration
- `!info` - Get information about the shape
- `!web` - Search the web (now free for all users)
- `!help` - Get help with commands
- `!imagine` - Generate images
- `!wack` - Reset the Shape's short-term memory

## Advanced Features

| Feature | Details |
|---------|---------|
| Vision Support | Send OpenAI API compatible image_url with user messages |
| Tool Calling | Shapes now support tool calling and MCP functionality |
| Voice Features | Free voice for all shapes (custom or pre-made voices via shapes.inc) |
| Voice Configuration | Option to disable voice transcripts (set via shapes.inc) |
| Voice Formatting | Improved formatting for voice URLs with new line separation |

## Important Notes

### Current Limitations

| Limitation | Details |
|------------|---------|
| No System Messages | Shape personality comes from configuration |
| No Message History | API relies on Shape's built-in memory |
| No Streaming | Only full responses are supported |
| No Parameter Control | Temperature and other settings locked to shapes.inc settings configured for the Shape |
| Extensions | Tool calling, Multi-agent Communication Protocol (MCP), vision support |

Note: Shapes set on Premium Engines **WILL** use credits when accessed via API.

## Available Integrations
- [x] Telegram
- [x] Revolt
- [x] Slack
- [x] Bluesky
- [x] IRC
- [x] Chess
- [x] Voice

## Requested Integrations
We're looking for developer contributions to build:
- [ ] Reddit
- [ ] GitHub (to review PRs)
- [ ] Threads
- [ ] Roblox
- [ ] Minecraft
- [ ] Twitch
- [ ] LinkedIn
- [ ] Microsoft Teams
- [ ] WeChat
- [ ] Anything you can possibly imagine

If you'd like to build an integration:
1. Fork our repository
2. Build your integration following our guidelines
3. Submit a PR with comprehensive documentation

## Coming Soon
We are shipping new features to the Shapes API every day. Next on our list is:

| Feature | Details |
|------------|---------|
| Voice Recognition | Shapes can send voice messages but not hear any yet |
| Authorize with Shapes, Inc | Authenticate users via a shapes inc account |
| Free Will | Proactively take actions |
| Messaging first | Shapes can't talk first...yet |

---
© 2025 Shapes, Inc.
