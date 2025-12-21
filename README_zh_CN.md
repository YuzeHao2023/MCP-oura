# Oura MCP 服务器

简体中文 | [English](./README.md) | 한국어

![Python Package](https://github.com/tomekkorbak/oura-mcp-server/workflows/Python%20Package/badge.svg)
[![PyPI version](https://badge.fury.io/py/oura-mcp-server.svg)](https://badge.fury.io/py/oura-mcp-server)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.12](https://img.shields.io/badge/python-3.12-blue.svg)](https://www.python.org/downloads/release/python-3120/)

一个基于[模型上下文协议](https://modelcontextprotocol.io/introduction)（MCP）的服务器，提供对 Oura API 的访问。它允许语言模型查询来自 Oura API 的睡眠、准备度和恢复力数据。

<a href="https://glama.ai/mcp/servers/@YuzeHao2023/MCP-oura">
  <img width="380" height="200" src="https://glama.ai/mcp/servers/@YuzeHao2023/MCP-oura/badge" alt="Oura Server MCP server" />
</a>

## 所有文档

> 寻找翻译志愿者！[我们正在寻找翻译志愿者](https://github.com/YuzeHao2023/MCP-oura/issues/5)来帮助为所有人翻译此规范！

**使用以下语言阅读我们的文档：**

| 语言    | 链接                                                            |
| ------- | --------------------------------------------------------------- |
| English | [English](https://github.com/YuzeHao2023/MCP-oura/README.md)    |
| 中文    | [中文](https://github.com/YuzeHao2023/MCP-oura/README_zh_CN.md) |
| 한국어  | [한국어](https://github.com/YuzeHao2023/MCP-oura/README_ko.md) |

## 可用工具

服务器提供以下工具：

### 日期范围查询

- `get_sleep_data(start_date: str, end_date: str)`：获取特定日期范围内的睡眠数据
- `get_readiness_data(start_date: str, end_date: str)`：获取特定日期范围内的准备度数据
- `get_resilience_data(start_date: str, end_date: str)`：获取特定日期范围内的恢复力数据

日期应以 ISO 格式（`YYYY-MM-DD`）提供。

### 今日数据查询

- `get_today_sleep_data()`：获取今天的睡眠数据
- `get_today_readiness_data()`：获取今天的准备度数据
- `get_today_resilience_data()`：获取今天的恢复力数据

## 使用方法

您需要一个 Oura API 令牌才能使用此服务器。您可以通过以下方式获取：

1. 访问 [Oura 开发者门户](https://cloud.ouraring.com/v2/docs)
2. 创建一个个人访问令牌

### Claude for Desktop

更新您的 `claude_desktop_config.json` 文件（在 macOS 上位于 `~/Library/Application\ Support/Claude/claude_desktop_config.json`，在 Windows 上位于 `%APPDATA%/Claude/claude_desktop_config.json`）以包含以下内容：

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

## 示例查询

连接后，您可以向 Claude 提出以下问题：

- "我今天的睡眠评分是多少？"
- "显示我过去一周的准备度数据"
- "我从 1 月 1 日到 1 月 7 日的睡眠情况如何？"
- "我今天的恢复力评分是多少？"

## 错误处理

服务器为常见问题提供人性化的错误消息：

- 无效的日期格式
- API 认证错误
- 网络连接问题

## 许可证

本项目采用 MIT 许可证 - 详情请参阅 LICENSE 文件。

---

## 维护者

<div align="center">
  <h4 align="center">
    维护者负责项目的维护、决策和长期发展。
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

## 核心贡献者

<div align="center">
  <h4 align="center">
    核心贡献者是项目的基石。
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
</div>
