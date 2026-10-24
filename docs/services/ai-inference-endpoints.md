# AI Model Inference & LLM Serving

Host open-source AI models (Llama, Mistral, Whisper, Stable Diffusion) and custom ML inference pipelines.

---

## Features
- **GPU & High-Compute Nodes**: Dedicated AMD Zen 5 and high-memory instances optimized for PyTorch, vLLM, and ONNX Runtime.
- **Model Weight Caching**: High-speed local NVMe caches reduce model load times from minutes to seconds.
- **Streaming Response Support**: Native Server-Sent Events (SSE) and WebSocket streaming for interactive token generation.

---

## Configuration Example (`hostly.toml`)

```toml
[[services]]
name = "llama-api"
type = "web"
routes = ["ai.hostly.dev"]
cmd = ["vllm", "serve", "meta-llama/Llama-3.2-3B-Instruct", "--port", "8000"]

[services.resources]
vcpu = 8.0
memory = "16384MB"
```
