# MOS MCP Server Plugin

A [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) server plugin for MOS (MountainOS). Enables AI assistants like Claude to interact with your MOS system.

## Features

- **70+ Tools** covering all MOS API functionality
- **System Management** - Monitor CPU, memory, temperature, network
- **Storage** - Manage disks, pools, shares
- **Containers** - Docker, LXC, and VM management
- **Configuration** - System settings, cron jobs, notifications

## Installation

Install via MOS Hub or manually:

1. Download the latest release
2. Install the .deb package: `dpkg -i mos-mcp-server_*.deb`

## Configuration

Settings are stored in `/boot/optional/plugins/mcp-server/settings.json`:

```json
{
  "api_url": "/api",
  "auth_method": "token",
  "enabled": true
}
```

## Usage with Claude Desktop

Add to your Claude Desktop configuration:

```json
{
  "mcpServers": {
    "mos": {
      "command": "node",
      "args": ["/opt/mos-mcp-server/src/index.js"],
      "env": {
        "MOS_API_URL": "http://your-mos-server/api",
        "MOS_API_TOKEN": "your-jwt-token"
      }
    }
  }
}
```

## Service Management

```bash
# Start/Stop/Restart
/etc/init.d/mos-mcp-server start
/etc/init.d/mos-mcp-server stop
/etc/init.d/mos-mcp-server restart

# Check status
/etc/init.d/mos-mcp-server status

# View logs
tail -f /var/log/mos-mcp-server.log
```

## Available Tools

See the full documentation in the [MOS API Documentation](https://github.com/ich777/mos-api/blob/master/DOCUMENTATION.md).

## License

ISC

## Author

RiDDiX
