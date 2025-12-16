# Oura MCP Server

[简体中文](./README_zh_CN.md) | English

![Python Package](https://github.com/tomekkorbak/oura-mcp-server/workflows/Python%20Package/badge.svg)
[![PyPI version](https://badge.fury.io/py/oura-mcp-server.svg)](https://badge.fury.io/py/oura-mcp-server)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.12](https://img.shields.io/badge/python-3.12-blue.svg)](https://www.python.org/downloads/release/python-3120/)

A [Model Context Protocol](https://modelcontextprotocol.io/introduction) (MCP) server that provides access to the Oura API. It allows language models to query sleep, readiness, and resilience data from Oura API.

<a href="https://glama.ai/mcp/servers/@YuzeHao2023/MCP-oura">
  <img width="380" height="200" src="https://glama.ai/mcp/servers/@YuzeHao2023/MCP-oura/badge" alt="Oura Server MCP server" />
</a>

## All Documents

> Call for translators! [We're looking for translators](https://github.com/YuzeHao2023/MCP-oura/issues/5) to help translate this spec for everyone!

**Read our documentation in the following languages:**

| Language | Link                                                            |
| -------- | --------------------------------------------------------------- |
| English  | [English](https://github.com/YuzeHao2023/MCP-oura/README.md)    |
| 中文     | [中文](https://github.com/YuzeHao2023/MCP-oura/README_zh_CN.md) |

## Available Tools

The server exposes the following tools:

### Date Range Queries

- `get_sleep_data(start_date: str, end_date: str)`: Get sleep data for a specific date range
- `get_readiness_data(start_date: str, end_date: str)`: Get readiness data for a specific date range
- `get_resilience_data(start_date: str, end_date: str)`: Get resilience data for a specific date range

Dates should be provided in ISO format (`YYYY-MM-DD`).

### Today's Data Queries

- `get_today_sleep_data()`: Get sleep data for today
- `get_today_readiness_data()`: Get readiness data for today
- `get_today_resilience_data()`: Get resilience data for today

## Usage

You'll need an Oura API token to use this server. You can obtain one by:

1. Going to the [Oura Developer Portal](https://cloud.ouraring.com/v2/docs)
2. Creating a Personal Access Token

### Claude for Desktop

Update your `claude_desktop_config.json` (located in `~/Library/Application\ Support/Claude/claude_desktop_config.json` on macOS and `%APPDATA%/Claude/claude_desktop_config.json` on Windows) to include the following

```json
{
  "mcpServers": {
    "oura": {
      "command": "uvx",
      "args": ["oura-mcp-server"],
      "env": {
        "OURA_API_TOKEN": "YOUR_OURA_API_TOKEN"
      }
    }
  }
}
```

## Example Queries

Once connected, you can ask Claude questions like:

- "What's my sleep score for today?"
- "Show me my readiness data for the past week"
- "How was my sleep from January 1st to January 7th?"
- "What's my resilience score today?"

## Error Handling

The server provides human-readable error messages for common issues:

- Invalid date formats
- API authentication errors
- Network connectivity problems

## License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## Maintainer

<div align="center">
  <h4 align="center">
    Maintainers oversee the project's maintenance, decision-making, and long-term development.
  </h4>
  <!-- 替换以下占位符为实际维护者信息 -->
  <a href="https://github.com/YuzeHao2023" target="_blank">
    <img src="https://github.com/YuzeHao2023.png" width="100" height="100" style="border-radius: 50%; margin: 0 10px; object-fit: cover;" alt="YuzeHao2023" />
  </a>
  <a href="https://github.com/dvlan26" target="_blank">
    <img src="https://github.com/dvlan26.png" width="100" height="100" style="border-radius: 50%; margin: 0 10px; object-fit: cover;" alt="dvlan26" />
  </a>
  <!-- 如需添加更多维护者，复制上方a标签块并修改信息即可 -->
</div>

## Core Contributors

<div align="center">
  <h4 align="center">
    The core contributors are the cornerstone of the project.
  </h4>
  <a href="https://github.com/YuzeHao2023" target="_blank">
    <img src="https://github.com/YuzeHao2023.png" width="100" height="100" style="border-radius: 50%; margin: 0 10px; object-fit: cover;" alt="YuzeHao2023" />
  </a>
  <a href="https://github.com/dvlan26" target="_blank">
    <img src="https://github.com/dvlan26.png" width="100" height="100" style="border-radius: 50%; margin: 0 10px; object-fit: cover;" alt="dvlan26" />
  </a>  
  <a href="https://github.com/halamji" target="_blank">
    <img src="https://github.com/halamji.png" width="100" height="100" style="border-radius: 50%; margin: 0 10px; object-fit: cover;" alt="halamji" />
  </a>
  <a href="https://github.com/yzhao112" target="_blank">
    <img src="https://github.com/yzhao112.png" width="100" height="100" style="border-radius: 50%; margin: 0 10px; object-fit: cover;" alt="yzhao112" />
  </a>
  <a href="https://github.com/punkpeye" target="_blank">
    <img src="https://github.com/punkpeye.png" width="100" height="100" style="border-radius: 50%; margin: 0 10px; object-fit: cover;" alt="punkpeye" />
  </a>
  <a href="https://github.com/iMilesHo" target="_blank">
    <img src="https://github.com/iMilesHo.png" width="100" height="100" style="border-radius: 50%; margin: 0 10px; object-fit: cover;" alt="iMilesHo" />
  </a>
  <a href="https://github.com/Vtwonine" target="_blank">
    <img src="https://github.com/Vtwonine.png" width="100" height="100" style="border-radius: 50%; margin: 0 10px; object-fit: cover;" alt="Vtwonine" />
  </a>
</div>
