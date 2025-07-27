# AG-UI CLI Agent

A command-line interface application built with AG-UI and Mastra framework, demonstrating real-time agent interactions with tool capabilities.

## Overview

This CLI agent showcases the AG-UI protocol implementation with:
- **Real-time streaming responses** from the AI agent
- **Tool integration** with weather API and web browser functionality
- **Persistent memory** using LibSQL storage
- **Event-driven communication** with detailed callback handling

## Architecture

- **Framework**: Mastra with AG-UI integration
- **Model**: OpenAI GPT-4o-mini
- **Memory**: LibSQL database storage (`mastra.db`)
- **Tools**: Weather API and browser launcher

### Project Structure

```
src/
├── index.ts          # CLI chat loop and event handlers
├── agent.ts          # Agent configuration and setup
└── tools/
    ├── weather.tool.ts    # Weather data fetching
    └── browser.tool.ts    # Web browser launcher
```

## Setup

### Prerequisites

- Node.js (v20+)
- OpenAI API key

### Installation

```bash
# Install dependencies
npm install

# Set up environment variables
cp .env.example .env
# Edit .env and add your OpenAI API key
```

## Usage

### Development Mode (with hot reload)

```bash
npm run dev
```

### Production Mode

```bash
npm start
```

### Available Commands

Once running, you can interact with the agent:

- **Weather queries**: "What's the weather in New York?"
- **Web browsing**: "Open https://www.example.com"
- **General conversation**: Ask any questions or request assistance

### CLI Interface

The application provides real-time feedback with:
- 🤖 **Agent responses**: Streamed text output
- 🔧 **Tool calls**: Shows when tools are being executed
- 🔍 **Tool results**: Displays tool execution results
- ❌ **Error handling**: Clear error messages

## Features

### Weather Tool
- Fetches current weather data using Open-Meteo API
- Provides temperature, humidity, wind conditions
- Includes location geocoding
- Weather condition interpretation

### Browser Tool
- Opens URLs in the default system browser
- Validates and handles full URL formats
- Provides execution feedback

### Memory System
- Persistent conversation history
- LibSQL database storage
- Thread-based conversation tracking

## Development

### Build

```bash
npm run build
```

### Clean

```bash
npm run clean
```

## AG-UI Integration

This example demonstrates key AG-UI concepts:

1. **Event Handlers**: Real-time streaming with callbacks
   - `onTextMessageStartEvent`: Message initiation
   - `onTextMessageContentEvent`: Streaming content deltas
   - `onToolCallStartEvent`: Tool execution begin
   - `onToolCallResultEvent`: Tool results display

2. **Agent Wrapper**: `MastraAgent` bridges Mastra framework with AG-UI protocol

3. **State Management**: Thread-based conversation persistence

## Configuration

### Environment Variables

Copy `.env.example` to `.env` and configure:

```bash
cp .env.example .env
```

Required variables:
- `OPENAI_API_KEY` - Your OpenAI API key

Optional variables:
- `OPENAI_MODEL` - Model to use (defaults to gpt-4o-mini)
- `DATABASE_URL` - Database path (defaults to file:./mastra.db)

### Agent Configuration

The agent is configured in `src/agent.ts` with:
- Model selection and parameters
- System instructions and behavior
- Tool registration and availability
- Memory storage configuration

Modify the instructions or add new tools by editing the agent configuration.