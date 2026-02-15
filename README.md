# Forex Analysis Bot with Telegram & Discord Alerts



<img width="338" height="160" alt="Ekran Görüntüsü_20260214_225711" src="https://github.com/user-attachments/assets/319dbdc7-d9b6-4c08-b307-9af5b1c032f6" />



This repository contains a professional-grade automation workflow designed to bridge Telegram market data with Discord analysis channels. The system utilizes n8n as the central orchestration engine, employing custom bot integrations to bypass standard platform limitations.



<img width="375" height="166" alt="Ekran Görüntüsü_20260214_225946" src="https://github.com/user-attachments/assets/35a5ea18-7eb9-493b-a6cf-394eac5e8a0a" />



# Overview

The architecture is engineered for low-latency command parsing and multi-platform distribution. It ingests technical requests from Telegram and outputs structured analytical data to Discord using a specialized trigger mechanism.

# System Architecture

Figure 1: n8n logic flow including regex-based command routing and API integration.

# Command Structure

The workflow is optimized to recognize and process specific triggers across both platforms:

# Telegram Commands:

/trend

/volatility

/liquidity

# Discord Commands (via n8n-trigger):

x Command: Makes trend Analysis.

y Command: Makes volatility analysis.

z Command: Makes liquidity analysis.

# Implementation & Integration
1. Telegram Ingestion
Obtain an API Token from @BotFather.

Configure the Telegram Trigger node in n8n to monitor specific group IDs.

Implement a Switch node to route incoming strings based on the command prefix.

# 2. Discord n8n-Trigger Bot Setup
Since n8n lacks a native Discord Trigger node, this workflow utilizes an external n8n-trigger bot gateway.

Figure 2: Discord bot configuration and channel mapping.

# Setup Procedure:

Bot Deployment: Invite the n8n-trigger bot to your Discord server.

Channel Configuration: Use the following command in the specific channels you wish the bot to monitor:

/setup webhook: [YOUR_N8N_WEBHOOK_URL]

# ID Mapping: 

Once the setup command is executed, the bot automatically maps the Channel IDs and Server IDs to the n8n webhook, ensuring all incoming messages from those specific environments are routed to the workflow, you need to manually replace Channel IDs.

# Technical Logic & Scalability
The core analysis is performed via a dedicated JavaScript node within n8n.

# Technical Note: 

The current analysis script utilizes a foundational logic set for trend identification. It is important to note that this is a base-level implementation. The code is designed to be highly modular and extensible; it can be further developed to include complex quantitative models, machine learning heuristics, or advanced statistical indicators without requiring a restructure of the integration pipeline.

# Technical Stack
Orchestration: n8n (Self-hosted)

Ingestion: Telegram Bot API

Trigger Mechanism: n8n-trigger Discord Bot

Logic: Node.js / JavaScript

# Disclaimer

This software is provided for informational purposes. All financial data interpretations are algorithmic and do not constitute financial advice.

[![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/requiemdrect)
