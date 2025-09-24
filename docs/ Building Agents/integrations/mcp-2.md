---
title: MCP
excerpt: Send requests to any MCP (Model Context Protocol) server.
deprecated: false
hidden: true
metadata:
  robots: index
---
With the MCP tool, your agent can connect to any MCP server directly from within the Agent step or Tool step. This allows you to bring in data, trigger external actions, or use custom logic that lives outside of Voiceflow. It’s helpful when you want your AI agent to be able to access external services that don't have built-in [Integration tools](doc:integrations).

<Callout icon="ℹ️" theme="info">
  MCP, or Model Context Protocol, is a standardized way for your agent to connect to external services. Think of it as a layer on top of an API that gives the agent context on how to use the API. [You can learn more about MCP here](https://modelcontextprotocol.io/docs/getting-started/intro).
</Callout>

<br />

## Basic usage

To connect to a MCP server from inside your Voiceflow agent, the server must be hosted and accessible from the internet. Local MCP servers are not supported by Voiceflow. You can find a [list of self-hosted, officially supported MCP servers here](https://github.com/modelcontextprotocol/servers?tab=readme-ov-file#%EF%B8%8F-official-integrations), or can use a tool such as [Zapier MCP](https://docs.zapier.com/mcp/home) to build a hosted MCP server.

<br />
