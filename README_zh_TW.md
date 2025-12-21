# Oura MCP Server

[简体中文](./README_zh_CN.md) | English | 한국어

![Python Package](https://github.com/tomekkorbak/oura-mcp-server/workflows/Python%20Package/badge.svg)
[![PyPI version](https://badge.fury.io/py/oura-mcp-server.svg)](https://badge.fury.io/py/oura-mcp-server)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.12](https://img.shields.io/badge/python-3.12-blue.svg)](https://www.python.org/downloads/release/python-3120/)

一個提供存取 Oura API 的 Model Context Protocol (MCP) 伺服器。它允許語言模型查詢睡眠、準備度和彈性資料 fro[...]

<a href="https://glama.ai/mcp/servers/@YuzeHao2023/MCP-oura">
  <img width="380" height="200" src="https://glama.ai/mcp/servers/@YuzeHao2023/MCP-oura/badge" alt="Oura Server MCP server" />
</a>

## 所有文件

> 徵求翻譯者！[我們正在尋找翻譯者](https://github.com/YuzeHao2023/MCP-oura/issues/5) 來幫助將此規格翻譯給所有人！

**請在下列語言閱讀我們的文件：**

| 語言     | 連結                                                            |
| -------- | --------------------------------------------------------------- |
| English  | [English](https://github.com/YuzeHao2023/MCP-oura/README.md)    |
| 中文     | [中文](https://github.com/YuzeHao2023/MCP-oura/README_zh_CN.md) |
| 한국어   | [한국어](https://github.com/YuzeHao2023/MCP-oura/README_ko.md) |

## 可用工具

伺服器公開下列工具：

### 日期範圍查詢

- `get_sleep_data(start_date: str, end_date: str)`: 取得特定日期範圍的睡眠資料
- `get_readiness_data(start_date: str, end_date: str)`: 取得特定日期範圍的準備度資料
- `get_resilience_data(start_date: str, end_date: str)`: 取得特定日期範圍的彈性資料

日期請以 ISO 格式提供（`YYYY-MM-DD`）。

### 今日資料查詢

- `get_today_sleep_data()`: 取得今天的睡眠資料
- `get_today_readiness_data()`: 取得今天的準備度資料
- `get_today_resilience_data()`: 取得今天的彈性資料

## 使用方式

您需要一個 Oura API 存取權杖 (API token) 才能使用此伺服器。您可以透過以下方式取得：

1. 前往 [Oura Developer Portal](https://cloud.ouraring.com/v2/docs)
2. 建立一個 Personal Access Token

### Claude for Desktop

更新您的 `claude_desktop_config.json`（macOS 位於 `~/Library/Application\ Support/Claude/claude_desktop_config.json`，Windows 位於 `%APPDATA%/Claude/claude_desktop_config.json`）以 includ[...]

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

## 範例查詢

連線後，您可以向 Claude 詢問例如：

- 「我今天的睡眠分數是多少？」
- 「顯示我過去一週的準備度資料」
- 「我 1 月 1 日到 1 月 7 日的睡眠情況如何？」
- 「我今天的彈性分數是多少？」

## 錯誤處理

伺服器會對常見問題提供可讀性高的錯誤訊息：

- 無效的日期格式
- API 認證錯誤
- 網路連線問題

## 授權

本專案採用 MIT 授權 - 詳見 LICENSE 檔案以取得詳細資訊。

---

## 維護者

<div align="center">
  <h4 align="center">
    維護者負責專案的維護、決策與長期發展。
  </h4>
  <!-- 替換以下占位符為實際維護者信息 -->
  <a href="https://github.com/YuzeHao2023" target="_blank">
    <img src="https://github.com/YuzeHao2023.png" width="100" height="100" style="border-radius: 50%; margin: 0 10px; object-fit: cover;" alt="YuzeHao2023" />
  </a>
  <a href="https://github.com/dvlan26" target="_blank">
    <img src="https://github.com/dvlan26.png" width="100" height="100" style="border-radius: 50%; margin: 0 10px; object-fit: cover;" alt="dvlan26" />
  </a>
  <!-- 如需添加更多維護者，複製上方a標籤塊並修改信息即可 -->
</div>

## 核心貢獻者

<div align="center">
  <h4 align="center">
    核心貢獻者是專案的基石。
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
```
