# Local LLM Lab
 
> Privacy-first AI inference infrastructure: local model hosting,
> API-accessible endpoints, and workflow automation without cloud dependencies.
 
## What This Is
 
A self-hosted AI stack built on commodity hardware, providing:
- **Private inference**: All model inference happens on-device. No data leaves the network.
- **API-compatible endpoints**: OpenAI-compatible REST API for integration with other tools
- **Web interface**: Open WebUI for interactive model use and prompt management
<!--
- **Workflow automation**: n8n for automated AI-assisted pipelines
-->
 
## Stack
 
| Component | Role | Why This Choice |
|-----------|------|-----------------|
| Ollama | Model Serving + API | OpenAI-compatible API, simple model management, GPU support |
| Open WebUI | Chat interface + model management | Feature-rich, self-hostable, supports multiple backends |
| RTX 3060 12Gb | Inference compute | VRAM: 6Gb, RAM: 8Gb, Cores: 3,584, BW: ~346Gb/s |
<!--
| n8n | Workflow automation | Visual automation with AI nodes, self-hostable, extensive integrations |
-->

 
## Models Running
 
| Model | Parameters | Use Case | Performance Notes |
|-------|-----------|----------|------------------|
| llama3.1 | 8B | Tool Use | 53 tok/s |
| qwen3.5 | 9B | Tool Use | 53 tok/s |

<!--
## Architecture
 
[Diagram of how components connect]
-->
 
## API Usage Example - Query local Ollama API

```console
curl http://localhost:11434/v1/chat/completions \
    -H "Content-Type: application/json" \
    -d '{
         "model": "llama3.2",
         "messages": [{"role": "user", "content": "Explain VLAN tagging"}]
}' 
```

## Skills Demonstrated
- REST API integration and testing
- Inference hardware selection and optimization
- Privacy-focused architecture design
- Workflow automation with AI integration
- Documentation of technical infrastructure decisions
