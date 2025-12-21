# Oura MCP 서버

[简体中文](./README_zh_CN.md) | English | 한국어

![Python Package](https://github.com/tomekkorbak/oura-mcp-server/workflows/Python%20Package/badge.svg)
[![PyPI version](https://badge.fury.io/py/oura-mcp-server.svg)](https://badge.fury.io/py/oura-mcp-server)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.12](https://img.shields.io/badge/python-3.12-blue.svg)](https://www.python.org/downloads/release/python-3120/)

[Model Context Protocol](https://modelcontextprotocol.io/introduction) (MCP)를 통해 Oura API에 접근할 수 있는 서버입니다. 이 서버는 언어 모델이 Oura API로부터 수집된 수면, 준비도(readiness), 회복력(resilience) 데이터를 질의할 수 있게 합니다.

<a href="https://glama.ai/mcp/servers/@YuzeHao2023/MCP-oura">
  <img width="380" height="200" src="https://glama.ai/mcp/servers/@YuzeHao2023/MCP-oura/badge" alt="Oura Server MCP server" />
</a>

## 모든 문서

> 번역자를 찾습니다! [우리는 번역자를 찾고 있습니다](https://github.com/YuzeHao2023/MCP-oura/issues/5) — 이 사양을 더 많은 사람에게 제공할 수 있게 도와주세요!

**다음 언어로 문서를 읽을 수 있습니다:**

| Language | Link                                                            |
| -------- | --------------------------------------------------------------- |
| English  | [English](https://github.com/YuzeHao2023/MCP-oura/README.md)    |
| 中文     | [中文](https://github.com/YuzeHao2023/MCP-oura/README_zh_CN.md) |
| 한국어   | [한국어](https://github.com/YuzeHao2023/MCP-oura/README_ko.md) |

## 사용 가능한 도구

서버는 다음과 같은 도구들을 제공합니다:

### 날짜 범위 질의

- `get_sleep_data(start_date: str, end_date: str)`: 특정 날짜 범위의 수면 데이터 조회
- `get_readiness_data(start_date: str, end_date: str)`: 특정 날짜 범위의 준비도 데이터 조회
- `get_resilience_data(start_date: str, end_date: str)`: 특정 날짜 범위의 회복력 데이터 조회

날짜는 ISO 형식(`YYYY-MM-DD`)으로 제공해야 합니다.

### 오늘 데이터 질의

- `get_today_sleep_data()`: 오늘의 수면 데이터 조회
- `get_today_readiness_data()`: 오늘의 준비도 데이터 조회
- `get_today_resilience_data()`: 오늘의 회복력 데이터 조회

## 사용법

이 서버를 사용하려면 Oura API 토큰이 필요합니다. 얻는 방법:

1. [Oura Developer Portal](https://cloud.ouraring.com/v2/docs)에 접속
2. Personal Access Token 생성

### Claude for Desktop

`claude_desktop_config.json` (macOS: `~/Library/Application\ Support/Claude/claude_desktop_config.json`, Windows: `%APPDATA%/Claude/claude_desktop_config.json`)을 다음과 같이 업데이트하세요:

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

## 예시 질의

연결되면 Claude에게 다음과 같이 물어볼 수 있습니다:

- "오늘 내 수면 점수는 얼마인가요?"
- "지난 주의 준비도 데이터를 보여주세요"
- "1월 1일부터 1월 7일까지의 수면은 어땠나요?"
- "오늘의 회복력 점수는 얼마인가요?"

## 오류 처리

서버는 다음과 같은 일반적인 문제에 대해 사람이 읽기 쉬운 오류 메시지를 제공합니다:

- 잘못된 날짜 형식
- API 인증 오류
- 네트워크 연결 문제

## 라이선스

이 프로젝트는 MIT 라이선스가 적용됩니다 - 자세한 내용은 LICENSE 파일을 참조하세요.

---

## 메인테이너

<div align="center">
  <h4 align="center">
    메인테이너는 프로젝트의 유지·결정·장기 개발을 담당합니다.
  </h4>
  <a href="https://github.com/YuzeHao2023" target="_blank">
    <img src="https://github.com/YuzeHao2023.png" width="100" height="100" style="border-radius: 50%; margin: 0 10px; object-fit: cover;" alt="YuzeHao2023" />
  </a>
  <a href="https://github.com/dvlan26" target="_blank">
    <img src="https://github.com/dvlan26.png" width="100" height="100" style="border-radius: 50%; margin: 0 10px; object-fit: cover;" alt="dvlan26" />
  </a>
</div>

## 핵심 기여자

<div align="center">
  <h4 align="center">
    핵심 기여자는 프로젝트의 초석입니다.
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


