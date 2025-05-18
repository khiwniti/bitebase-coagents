# BiteBase CoAgents - Restaurant Market Research Platform

![BiteBase Logo](coagents-market-research/agent/static/agent-diagram.png)

## Overview

BiteBase CoAgents is an advanced restaurant market research platform that leverages AI agents to provide comprehensive analysis and insights for restaurant owners and operators. The platform combines specialized AI agents, workflow orchestration, and fine-tuned models to deliver actionable intelligence across product, price, place, and promotion domains.

## Key Features

- **Restaurant Data Collection**: Gather restaurant data from multiple platforms (Foodpanda, Wongnai, Robinhood, Google Maps)
- **Cross-Platform Matching**: Match restaurants across different platforms for comprehensive analysis
- **Market Analysis**: Analyze restaurant market trends, competition, and opportunities
- **Location Intelligence**: Evaluate locations based on demographic data, foot traffic, and competition
- **Menu Optimization**: Analyze menu performance and suggest improvements
- **Interactive Visualization**: Visualize data with interactive maps and dashboards

## Project Structure

The project consists of two main components:

### 1. Agent System (`/agent`)

The agent system is responsible for data collection, analysis, and insights generation. It includes:

- **Core Framework**: Base agent architecture, API clients, and data processors
- **Specialized Agents**: Domain-specific agents for different types of analysis
- **API Server**: Express.js server for exposing agent capabilities via REST API
- **LLM Integration**: Support for multiple LLM providers (OpenAI, DeepSeek)

### 2. User Interface (`/ui`)

The UI provides an interactive interface for users to interact with the agent system. It includes:

- **Interactive Map**: Visualize restaurant locations and market data
- **Dashboard**: Display analysis results and insights
- **Chat Interface**: Interact with AI agents through natural language
- **Real-time Monitoring**: Track agent activities and system performance

## Getting Started

### Prerequisites

- Node.js 18+
- Python 3.10+
- MongoDB (optional, for data storage)
- API keys for:
  - OpenAI or DeepSeek (for LLM capabilities)
  - Google Maps (for location data)
  - Foodpanda, Wongnai, etc. (optional, for platform-specific data)

### Installation

#### Agent System

1. Navigate to the agent directory:
   ```bash
   cd coagents-market-research/agent
   ```

2. Install Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up environment variables:
   ```bash
   # Create .env file
   cp .env.example .env
   # Edit .env with your API keys
   ```

4. Set up DeepSeek API (optional):
   ```bash
   python set_api_key.py --provider deepseek --key YOUR_DEEPSEEK_API_KEY --test
   ```

#### User Interface

1. Navigate to the UI directory:
   ```bash
   cd coagents-market-research/ui
   ```

2. Install Node.js dependencies:
   ```bash
   npm install
   # or
   pnpm install
   ```

3. Set up environment variables:
   ```bash
   # Create .env file
   cp .env.example .env
   # Edit .env with your API keys
   ```

### Running the Application

#### Start the Agent Server

```bash
cd coagents-market-research/agent
node server.js
```

#### Start the UI Development Server

```bash
cd coagents-market-research/ui
npm run dev
# or
pnpm run dev
```

The application will be available at http://localhost:3001

## Architecture

### Agent Architecture

The agent system follows a modular architecture:

- **BaseAgent**: Foundation class for all agents with configuration, metrics, and error handling
- **APIClient**: Unified client for API requests with rate limiting, caching, and retries
- **LLMClient**: Client for interacting with language models (OpenAI, DeepSeek)
- **RestaurantDataAgent**: Collects and processes restaurant data from multiple sources
- **RestaurantAnalysisAgent**: Analyzes restaurant data and generates insights
- **RestaurantMatcher**: Matches restaurants across different platforms

### UI Architecture

The UI is built with Next.js and follows a component-based architecture:

- **MapCanvas**: Interactive map for visualizing restaurant locations
- **RestaurantDashboard**: Dashboard for displaying restaurant data and insights
- **CopilotSidebar**: Chat interface for interacting with AI agents
- **StatusPanel**: Real-time monitoring of agent activities
- **ApiMonitor**: Monitoring of API calls and responses
- **PerformanceMetrics**: System performance metrics visualization

## API Reference

### Restaurant Data API

- `GET /api/restaurants`: Get restaurant data for a specific location
  - Parameters: `latitude`, `longitude`, `radius`, `platforms` (optional)

- `GET /api/restaurants/match`: Match restaurants across platforms
  - Parameters: `latitude`, `longitude`, `radius`, `platforms` (optional)

- `GET /api/analyze`: Analyze restaurant data
  - Parameters: `latitude`, `longitude`, `radius`, `platforms` (optional), `analysis_type` (optional)

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Open a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- [LangGraph](https://github.com/langchain-ai/langgraph) for agent orchestration
- [Next.js](https://nextjs.org/) for the UI framework
- [Leaflet](https://leafletjs.com/) for interactive maps
- [Framer Motion](https://www.framer.com/motion/) for animations
- [Tailwind CSS](https://tailwindcss.com/) for styling
- [CopilotKit](https://github.com/CopilotKit/CopilotKit) for chat interface

## Contact

For questions or support, please contact [support@bitebase.app](mailto:support@bitebase.app)
