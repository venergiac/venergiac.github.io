---
layout: post
title:  "Version 0.1 of OPCUA2MCP IIoT Bridge - released - connects to an OPC UA server, reads sensor values defined in YAML configuration, evaluates sensor health against configurable thresholds, caches readings, and publishes the results through a FastMCP server"
date:   2026-06-09 00:00:00 +0100
categories: article
---

# Version 0.1 of OPCUA2MCP IIoT Bridge - released

opcua2mcp is the core bridge module in src/opcua2mcp.py. It connects to an OPC UA server, reads sensor values defined in YAML configuration, evaluates sensor health against configurable thresholds, caches readings, and publishes the results through a FastMCP server.

The design is ideal for IIoT deployments that need:

- OPC UA data ingestion from equipment simulators or real PLCs
- MCP tool exposure for model context interoperability
- machine health scoring and alert generation
- optional Redis caching for faster repeated reads

the idea based on Agentic AIOT [https://venergiac.substack.com/p/agentic-aiot-the-future-of-manufacturing](https://venergiac.substack.com/p/agentic-aiot-the-future-of-manufacturing). 

Clone code from

     git clone https://github.com/venergiac/iiot-opcua2mcp.git