# 🛡️ OFAC, UN & EU Sanctions + GLEIF LEI Vendor KYB Gate

[![Marketplace Release](https://img.shields.io/github/v/release/jesleytassili-glitch/ofac-sanctions-kyb-action?color=brightgreen&label=Marketplace%20Release)](https://github.com/jesleytassili-glitch/ofac-sanctions-kyb-action/releases/tag/v1.0.0)
[![Official MCP Registry](https://img.shields.io/badge/Official_MCP_Registry-io.github.jesleytassili-glitch-6366F1)](https://registry.modelcontextprotocol.io/v0/servers?search=io.github.jesleytassili-glitch)
[![RapidAPI Hub](https://img.shields.io/badge/RapidAPI-@b2bquantapis-0055FF)](https://rapidapi.com/b2bquantapis/api/global-sanctions-pep-interpol-watchlist-screener)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](./LICENSE)

Automated CI/CD supplier onboarding gate for OFAC SDN, UN, EU sanctions screening and GLEIF LEI corporate ownership KYB.

## 🚀 Quick Start (`.github/workflows/compliance.yml`)

```yaml
name: Automated Compliance Audit
on:
  pull_request:
  schedule:
    - cron: '0 7 * * 1'

jobs:
  audit:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Run OFAC, UN & EU Sanctions + GLEIF LEI Vendor KYB Gate
        uses: jesleytassili-glitch/ofac-sanctions-kyb-action@v1
        with:
          mode: 'sanctions-screen'
          targets: 'Acme Global Trading Ltd,Siemens AG'
          rapidapi_key: ${{ secrets.RAPIDAPI_KEY }}
```

## 📊 Available Audit Modes

- `sanctions-screen` — OFAC, UN, EU & PEP Watchlist Screening ([RapidAPI](https://rapidapi.com/b2bquantapis/api/global-sanctions-pep-interpol-watchlist-screener) | [Apify](https://apify.com/b2b-quant-apis/global-sanctions-pep-interpol-watchlist-screener))
- `gleif-lei-kyb` — GLEIF LEI Corporate Ownership & Parent KYB ([RapidAPI](https://rapidapi.com/b2bquantapis/api/global-gleif-lei-corporate-ownership-kyb) | [Apify](https://apify.com/b2b-quant-apis/global-gleif-lei-corporate-ownership-kyb))

## 📦 Programmatic SDKs & Local MCP Server

- **Python SDK:** `pip install https://github.com/jesleytassili-glitch/b2b-compliance-python-sdk/releases/download/v1.0.0/b2b_compliance_sdk-1.0.0-py3-none-any.whl`
- **Node.js / Claude / Cursor MCP (`stdio`):** `npx --yes github:jesleytassili-glitch/b2b-compliance-mcp-cli`
