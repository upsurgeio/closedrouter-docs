# Pineapple API Documentation

A unified API router built in-house for [Bhindi.ai](https://bhindi.io) 🚀

ClosedRouter provides a **single gateway** to interact with multiple LLM providers (OpenAI, Anthropic, and more), with consistent authentication, response formats, and error handling.

## ✨ Key Features

With ClosedRouter you can:

- 🔐 **Manage users & API keys** - Secure user authentication and key management
- 🤖 **Chat (single-turn \+ multi-turn)** - Support for both conversation modes
- 📡 **Stream responses in real-time** - Get responses as they're generated
- 🛠️ **Perform tool calls** - Execute functions and tools through LLMs
- 🗂️ **Enforce structured outputs** - Get consistent, structured responses
- 🖼️ **Generate images** - Create images using various AI models
- ⚠️ **Handle standardized errors** - Consistent error handling across all endpoints

---

## 📖 Complete Documentation

[**📚 Read the Full Development Guide →**](./development-guide.mdx)

For detailed specifications, advanced examples, and the full API reference, see our complete guide.

---

## 📚 Table of Contents

- [🚀 Quick Start](#-quick-start)
- [🩺 Health & Models](#-health--models)
- [👤 User Management](#-user-management)
- [🔑 Authentication & API Keys](#-authentication--api-keys)
- [💬 Chat APIs](#-chat-apis)
- [📡 Streaming](#-streaming)
- [🛠 Tool Calls](#-tool-calls)
- [🗂 Structured Outputs](#-structured-outputs)
- [🖼 Image Generation](#-image-generation)
- [⚠️ Error Handling](#️-error-handling)
- [📖 Next Steps](#-next-steps)

---

## 🚀 Quick Start

### 3-Step Setup

#### 1. Register a User

```bash
POST /v1/register-user
```

#### 2. Create an API Key

```bash
POST /v1/create-api-key
```

#### 3. Send Your First Chat Request

```bash
POST /v1/chat/openai
Authorization: Bearer <api_key>

{
  "model": "gpt-4o",
  "messages": [
    {
      "role": "user", 
      "content": "Hello ClosedRouter!"
    }
  ]
}
```

---

## 🩺 Health & Models

### System Status

```bash
GET /v1/health
```

Check system status and availability.

### Available Models

```bash
GET /v1/models
```

Retrieve available models across OpenAI & Anthropic providers.

---

## 👤 User Management

### User Registration

```bash
POST /v1/register-user
```

Register a new user account.

### User Profile

```bash
GET /v1/user-profile
```

Fetch user details and account information.

---

## 🔑 Authentication & API Keys

ClosedRouter uses API keys for all requests.

### Generate API Key

```bash
POST /v1/create-api-key
```

Generate a new API key for authentication.

### Usage

Include the API key in every request header:

```bash
Authorization: Bearer <your_api_key>
```

---

## 💬 Chat APIs

### OpenAI-Compatible Endpoints

```bash
POST /v1/chat/openai          # Single-turn chat
POST /v1/chat/openai/multi-turn  # Multi-turn conversation
```

### Anthropic-Compatible Endpoints

```bash
POST /v1/chat/anthropic       # Single-turn chat
POST /v1/chat/anthropic/sys-message  # System message support
```

---

## 📡 Streaming

Stream responses token-by-token for real-time interaction:

```bash
POST /v1/stream/openai        # OpenAI streaming
POST /v1/stream/anthropic     # Anthropic streaming
```

---

## 🛠 Tool Calls

Execute functions and tools through LLM interactions:

```bash
POST /v1/tool-call/openai     # OpenAI tool calls
POST /v1/tool-call/anthropic  # Anthropic tool calls
POST /v1/tool-call/multi-turn-test  # Multi-turn tool testing
```

---

## 🗂 Structured Outputs

Get consistent, structured responses from your LLMs:

```bash
POST /v1/structured-output/openai     # OpenAI structured outputs
POST /v1/structured-output/anthropic  # Anthropic structured outputs
POST /v1/tool-call+structured         # Combined tool call + structured output flow
```

---

## 🖼 Image Generation

Create images using various AI models:

```bash
POST /v1/image/openai         # OpenAI image generation
POST /v1/image/anthropic      # Anthropic image generation
```

---

## ⚠️ Error Handling

ClosedRouter standardizes error responses across all endpoints for consistent error handling.

### Error Response Format

```json
{
  "error": {
    "message": "Invalid model ID",
    "code": "invalid_model"
  }
}
```

### Common Error Codes

- **Invalid Model** - Model ID not found or unsupported
- **Missing Auth Header** - Authorization header is required
- **Invalid API Key** - API key is invalid or expired
- **Rate Limit Exceeded** - Too many requests
- **Server Error** - Internal server error

---

## 📖 Next Steps

- **📚 Read the Development Guide** – Learn implementation details and advanced usage
- **💬 Test with Postman** – Use our Postman collection to explore APIs interactively
- **🚀 Build on Bhindi** – Integrate ClosedRouter into Bhindi AI applications
- **🔧 Check Examples** – Review code examples and integration patterns

---

<div align="center">
Built with ❤️ for the Bhindi AI ecosystem

</div>