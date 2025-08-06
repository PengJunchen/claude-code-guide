# MCP (Model Context Protocol) Servers

This directory contains configuration files for various MCP servers that can be used to extend the capabilities of LLMs.

## What is MCP?

The Model Context Protocol (MCP) enables communication between LLMs and locally running MCP servers that provide additional tools and resources to extend the capabilities of the LLMs.

## Available MCP Servers

### Browser Automation
- **Playwright**: Browser automation capabilities using Playwright

### Database Integration
- **PostgreSQL**: Integration with PostgreSQL databases
- **MySQL**: Integration with MySQL databases

### GitHub Integration
- **GitHub**: Integration with GitHub repositories, issues, pull requests, etc.

### Web Fetch
- **Web Fetch**: Capabilities to fetch content from web pages

## How to Use

To use an MCP server, you need to:

1. Install the required dependencies
2. Start the MCP server
3. Connect to the MCP server from your LLM

Example:

```bash
# Install Playwright MCP
npm install @playwright/mcp

# Start Playwright MCP server
npx @playwright/mcp

# Connect to the MCP server from your LLM
# This is typically done through the LLM's interface
```

## Adding New MCP Servers

To add a new MCP server, create a new JSON file with the following structure:

```json
{
  "mcpServers": {
    "server-name": {
      "description": "Description of the MCP server",
      "command": "command-to-run",
      "args": [
        "arg1",
        "arg2"
      ]
    }
  }
}
```

## Benefits of Using MCP

- **Extended Capabilities**: Access to tools and resources beyond the LLM's built-in capabilities
- **Local Execution**: Run tools locally without sending sensitive data to remote servers
- **Custom Tools**: Create custom tools tailored to your specific needs
- **Integration**: Integrate with existing systems and workflows