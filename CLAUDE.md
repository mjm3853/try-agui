# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is an experimental repository for exploring the AG-UI framework - an open protocol that standardizes how front-end applications connect to AI agents. The repository contains:

### Projects Structure
- `my-ag-ui-cli-app/` - Working CLI agent with Mastra framework
- Python exploration using uv package management
- Mixed language approach for comprehensive AG-UI testing

### Goals
- Testing AG-UI protocol implementation
- Exploring real-time agent interactions  
- Experimenting with human-in-the-loop workflows
- Building AI-powered front-end applications

## AG-UI Framework Context

AG-UI provides:
- Real-time interactivity with AI agents
- Live state streaming for dynamic updates
- Human-in-the-loop collaboration workflows
- Transport-agnostic communication (SSE, webhooks, WebSockets)
- Event-driven bidirectional communication
- Support for multiple agent frameworks (LangGraph, CrewAI, etc.)

The protocol focuses on the agent-user interaction layer, complementing A2A (agent-to-agent) and MCP (model context protocol).

## Development Environment

### Multi-Language Setup

This repository contains both Python and Node.js projects for comprehensive AG-UI exploration.

#### Python Environment (Root)
Uses [uv](https://docs.astral.sh/uv/) for package management:

**Requirements:**
- Python >=3.12 (as specified in pyproject.toml)
- uv package manager

**Common Commands:**
```bash
# Install dependencies and create virtual environment
uv sync

# Run Python scripts
uv run python script.py
uv run python hello.py  # Run the example script

# Add new dependencies
uv add package-name
uv add --dev package-name  # Development dependencies

# Run tests (when test framework is added)
uv run pytest

# Start Python REPL with project dependencies
uv run python
```

#### Node.js Environment (CLI App)
The `my-ag-ui-cli-app/` directory contains a TypeScript/Node.js project:

**Requirements:**
- Node.js v20+
- OpenAI API key

**Common Commands:**
```bash
cd my-ag-ui-cli-app

# Install dependencies
npm install

# Development mode (hot reload)
npm run dev

# Production mode
npm start

# Build TypeScript
npm run build

# Clean build artifacts
npm run clean
```

### Project Structure
- `pyproject.toml` - Python project configuration
- `uv.lock` - Python dependency lock file
- `hello.py` - Python example script
- `my-ag-ui-cli-app/` - Node.js CLI agent implementation
  - `package.json` - Node.js dependencies and scripts
  - `src/index.ts` - CLI chat interface
  - `src/agent.ts` - Agent configuration
  - `src/tools/` - Tool implementations (weather, browser)

## Key Resources

- [AG-UI Documentation](http://docs.ag-ui.com/introduction) - Primary reference for framework capabilities and implementation guides
- Framework supports multiple agent backends and provides building blocks for human-agent communication

## Development Notes

### Working with the CLI Agent
1. The CLI agent in `my-ag-ui-cli-app/` is fully functional
2. Requires OpenAI API key for operation
3. Demonstrates streaming responses and tool usage
4. Memory persists across sessions in `mastra.db`
5. Use `Ctrl+D` to exit the chat interface

### Experimental Nature
Expect:
- Rapid prototyping and iteration
- Multiple implementation approaches being tested
- Focus on understanding AG-UI protocol mechanics
- Integration experiments with different agent frameworks
- Both Python and Node.js implementations

### Adding New Tools
To extend the CLI agent:
1. Create new tool files in `src/tools/`
2. Follow the pattern in `weather.tool.ts` or `browser.tool.ts`
3. Register tools in `src/agent.ts`
4. Use `createTool` from `@mastra/core/tools`

## AG-UI Implementation Details

### Working CLI Agent Features
The `my-ag-ui-cli-app/` demonstrates key AG-UI concepts:

- **Real-time streaming**: `onTextMessageContentEvent` for delta updates
- **Tool integration**: Weather API and browser launcher tools
- **Memory persistence**: LibSQL database for conversation history
- **Event-driven architecture**: Comprehensive callback handling
- **Mastra framework**: Bridge between AG-UI protocol and agent logic

### Key Dependencies (CLI App)
- `@ag-ui/client`, `@ag-ui/core`, `@ag-ui/mastra` - AG-UI protocol implementation
- `@mastra/core`, `@mastra/client-js` - Agent framework
- `@ai-sdk/openai` - OpenAI integration
- `@mastra/memory`, `@mastra/libsql` - Persistent storage

### Python AG-UI Dependencies
When implementing Python AG-UI features:

```bash
# Potential Python packages for AG-UI
uv add fastapi uvicorn  # For web server/API
uv add websockets       # For WebSocket communication
uv add httpx           # For HTTP client requests
uv add pydantic        # For data validation
uv add langchain        # For LangChain integration
```

### Environment Variables
The CLI agent uses a `.env` file for configuration:

```bash
# Copy the example file
cp my-ag-ui-cli-app/.env.example my-ag-ui-cli-app/.env
# Edit .env to add your OpenAI API key
```

Required variables:
- `OPENAI_API_KEY` - Your OpenAI API key

Optional variables:
- `OPENAI_MODEL` - Model to use (defaults to gpt-4o-mini)
- `DATABASE_URL` - Database path (defaults to file:./mastra.db)

## Project Development Best Practices

### Repository Management
- Always update the root readme and claude markdown files after making code updates if those updates impact how the project is set up or how to run different project commands