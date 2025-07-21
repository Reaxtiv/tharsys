# THARSYS

<div align="center">
  <img src="https://raw.githubusercontent.com/tu-usuario/tharsys/main/public/logo.png" alt="THARSYS Logo" width="200">
</div>

### AI Agent Orchestration Platform  
*Build, deploy and manage autonomous AI systems at scale*

---

## Overview  
**THARSYS** is an open-source framework for creating stateful AI agent workflows with:  

- 🧩 **Modular Architecture** - Combine conversational, procedural, and specialized agents  
- ⚡ **Real-time Execution** - Low-latency inference engine  
- 📊 **Full Observability** - Built-in tracing, logging, and evaluation metrics  

Inspired by [a16z/ai-getting-started](https://github.com/a16z/ai-getting-started).

---

## Quick Start

### Prerequisites
- Node.js 20+
- Docker
- Python 3.10+ (for some dependencies)

```bash
# Clone repository
git clone https://github.com/tu-usuario/tharsys.git
cd tharsys

# Install dependencies
npm install
pip install -r requirements.txt

# Start services
docker compose up -d
npm run dev
Access the dashboard at: http://localhost:3000

Core Features
Component	Description	Configuration File
Agent Runtime	Execution environment for workflows	config/runtime.yaml
Model Gateway	Unified interface for LLMs	config/models.ts
Memory Engine	Vector + relational persistence	src/memory/
Configuration
1. Set Environment Variables
bash
cp .env.example .env
# Edit with your API keys
2. Connect AI Providers
Edit config/providers.ts:

typescript
export default {
  openai: {
    apiKey: process.env.OPENAI_KEY,
    defaultModel: 'gpt-4-turbo'
  },
  ollama: {
    endpoint: 'http://localhost:11434',
    defaultModel: 'llama3'
  }
}
Deployment Options
Option 1: Vercel (Frontend) + Convex (Backend)
https://vercel.com/button

Option 2: Docker Production
bash
docker compose -f docker-compose.prod.yml up --build
Option 3: Bare Metal
bash
npm run build
node dist/main.js
Troubleshooting
Logo Not Displaying?
Ensure the logo exists at /public/logo.png

Verify the raw GitHub URL is correct:

markdown
![Logo](https://raw.githubusercontent.com/tu-usuario/tharsys/main/public/logo.png)
Ollama Connection Issues
bash
# Test connection
curl http://localhost:11434/api/tags

# Set Docker-compatible host
npx convex env set OLLAMA_HOST="http://host.docker.internal:11434"
License
Apache 2.0 © [Your Organization] 2024
