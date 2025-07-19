# Open Deep Research

<img width="1388" height="298" alt="full_diagram" src="https://github.com/user-attachments/assets/12a2371b-8be2-4219-9b48-90503eb43c69" />

A comprehensive, open-source deep research agent that combines advanced AI capabilities with a modern web interface. This project provides both a powerful research backend built with LangGraph and a beautiful web frontend using Next.js and Assistant UI.

## 🌟 Features

- **Advanced Research Agent**: Multi-model, configurable research system with support for various search APIs and MCP servers
- **Modern Web Interface**: Beautiful, responsive web UI built with Next.js and Assistant UI
- **Multi-Provider Support**: Works with OpenAI, Anthropic, Google Vertex AI, and other model providers
- **Extensible Architecture**: Support for MCP (Model Context Protocol) servers to extend capabilities
- **Comprehensive Evaluation**: Built-in evaluation system for testing and benchmarking
- **Production Ready**: Easy deployment options for both backend and frontend

## 🏗️ Project Structure

```
open_deep_research/
├── agent/                 # Research agent backend
│   ├── src/
│   │   ├── open_deep_research/  # Main agent implementation
│   │   ├── legacy/              # Alternative implementations
│   │   └── security/            # Authentication and security
│   ├── tests/                   # Evaluation and testing
│   └── examples/                # Example configurations
└── web/                    # Web frontend
    ├── app/                 # Next.js app directory
    ├── components/          # React components
    └── lib/                 # Utility functions
```

## 🚀 Quick Start

### Prerequisites

- Python 3.10+ (for agent backend)
- Node.js 18+ (for web frontend)
- API keys for your chosen model providers

### 1. Clone and Setup

```bash
git clone https://github.com/langchain-ai/open_deep_research.git
cd open_deep_research
```

### 2. Backend Setup (Agent)

```bash
cd agent

# Create virtual environment
uv venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
uv pip install -r pyproject.toml

# Set up environment variables
cp .env.example .env
# Edit .env with your API keys and configuration
```

### 3. Frontend Setup (Web)

```bash
cd web

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env.local
# Edit .env.local with your configuration:
# LANGCHAIN_API_KEY=your_langchain_api_key
# LANGGRAPH_API_URL=your_langgraph_api_url
# NEXT_PUBLIC_LANGGRAPH_ASSISTANT_ID=your_assistant_id_or_graph_id
```

### 4. Start the Services

**Start the LangGraph server (Backend):**
```bash
cd agent
uvx --refresh --from "langgraph-cli[inmem]" --with-editable . --python 3.11 langgraph dev --allow-blocking
```

**Start the web frontend:**
```bash
cd web
npm run dev
```

### 5. Access the Application

- **Web UI**: http://localhost:3000
- **LangGraph Studio**: https://smith.langchain.com/studio/?baseUrl=http://127.0.0.1:2024
- **API Docs**: http://127.0.0.1:2024/docs

## ⚙️ Configuration

### Backend Configuration

The agent supports extensive configuration through environment variables:

```bash
# Model Configuration
OPENAI_API_KEY=your_openai_key
ANTHROPIC_API_KEY=your_anthropic_key

# Search Configuration
TAVILY_API_KEY=your_tavily_key
SEARCH_API=tavily  # Options: tavily, openai, anthropic, none

# Research Settings
MAX_RESEARCHER_ITERATIONS=3
MAX_CONCURRENT_RESEARCH_UNITS=5
ALLOW_CLARIFICATION=true
```

### Frontend Configuration

Configure the web interface in `.env.local`:

```bash
LANGCHAIN_API_KEY=your_langchain_api_key
LANGGRAPH_API_URL=http://127.0.0.1:2024
NEXT_PUBLIC_LANGGRAPH_ASSISTANT_ID=your_assistant_id
```

## 🔧 Advanced Features

### Model Providers

The system supports multiple model providers:

- **OpenAI**: GPT-4, GPT-3.5, and other OpenAI models
- **Anthropic**: Claude models with web search capability
- **Google Vertex AI**: PaLM and Gemini models
- **OpenRouter**: Access to multiple model providers
- **Local Models**: Via Ollama integration

### Search APIs

- **Tavily**: Works with all models
- **OpenAI Native Web Search**: Requires OpenAI models with web search
- **Anthropic Native Web Search**: Requires Anthropic models with web search
- **Custom**: Integrate your own search providers

### MCP (Model Context Protocol) Servers

Extend capabilities with MCP servers:

- **Filesystem MCP**: Secure file system operations
- **Remote MCP**: Distributed agent coordination
- **Custom MCP**: Build your own protocol servers

## 📊 Evaluation

Run comprehensive evaluations:

```bash
cd agent
python tests/run_evaluate.py
```

The evaluation system provides:
- Multi-dimensional scoring (0-1 scale)
- Batch processing across test cases
- Specialized evaluators for different aspects
- Comparative analysis capabilities

## 🚀 Deployment

### Backend Deployment

**LangGraph Platform:**
```bash
# Deploy to LangGraph Platform
langgraph deploy
```

**Open Agent Platform (OAP):**
1. [Deploy OAP](https://docs.oap.langchain.com/quickstart)
2. [Add Deep Researcher to OAP](https://docs.oap.langchain.com/setup/agents)

### Frontend Deployment

**Vercel (Recommended):**
```bash
cd web
npm run build
# Deploy to Vercel
```

**Other Platforms:**
```bash
cd web
npm run build
npm run start
```

## 🧪 Testing

### Backend Tests
```bash
cd agent
pytest tests/
```

### Frontend Tests
```bash
cd web
npm run lint
npm run build
```

## 📚 Documentation

- **Blog Post**: [Open Deep Research Blog](https://blog.langchain.com/open-deep-research/)
- **Video Overview**: [YouTube Demo](https://www.youtube.com/watch?v=agGiWUpxkhg)
- **Legacy Implementations**: See `agent/src/legacy/legacy.md` for alternative approaches

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](agent/LICENSE) file for details.

## 🙏 Acknowledgments

- Built with [LangGraph](https://github.com/langchain-ai/langgraph)
- Web UI powered by [Assistant UI](https://github.com/Yonom/assistant-ui)
- Research capabilities enhanced by [LangChain](https://github.com/langchain-ai/langchain)

## 🔗 Links

- **Repository**: https://github.com/langchain-ai/open_deep_research
- **Live Demo**: https://oap.langchain.com
- **Documentation**: https://docs.langchain.com
- **Community**: https://discord.gg/langchain 