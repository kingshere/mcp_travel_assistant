# 🌍 MCP Travel Concierge Server

A high-performance **Model Context Protocol (MCP)** server that bridges the gap between consumer-facing travel search and professional-grade **Global Distribution System (GDS)** inventory. 

Designed for **Agentic Workflows**, this server enables LLMs to perform real-time, deterministic travel optimization by unifying Google Travel Services with Amadeus Professional Systems.



## 🚀 Key Technical Features

### ✈️ Unified Dual-Provider Search
* **Amadeus GDS Integration:** Access to professional airline inventory, detailed fare classes, and real-time seat availability.
* **Google Travel Services (via SerpAPI):** Consumer-friendly pricing insights across flights, hotels, and local events.

### 🛠️ Agent-Centric Architecture
* **Standardized Tooling:** Built using the FastMCP framework to ensure seamless integration with Claude Desktop, Cursor, and custom agentic runners.
* **Transport Agnostic:** Supports **Stdio** for local AI communication and **SSE/HTTP** for distributed deployments.
* **Utility Layer:** Integrated geocoding (Nominatim), weather intelligence (Open-Meteo), and live currency conversion for end-to-end trip planning.

## 🏗️ Architecture & Design
* **Concurrency Control:** Engineered for concurrent request handling to reduce latency during multi-provider comparisons.
* **Stateful Lifespan Management:** Implements FastAPI-style lifespan handlers for secure environment variable validation and resource cleanup.
* **Rate Limiting:** Built-in protection for external API dependencies to ensure system stability under high-frequency agent tool calls.

## 🔧 MCP Integration (Claude/Cursor)
Add the following to your MCP configuration file:
{
  "mcpServers": {
    "travel-concierge": {
      "command": "python",
      "args": ["/absolute/path/to/travel_server.py"],
      "env": {
        "SERPAPI_KEY": "...",
        "AMADEUS_API_KEY": "...",
        "AMADEUS_API_SECRET": "..."
      }
    }
  }
}
AMADEUS_API_KEY=your_amadeus_key
AMADEUS_API_SECRET=your_amadeus_secret
EXCHANGE_RATE_API_KEY=your_exchange_rate_key
