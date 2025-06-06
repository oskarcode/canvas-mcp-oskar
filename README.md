# Canvas MCP Oskar

## Overview
A Model Context Protocol (MCP) implementation for Canvas integration built on Cloudflare Workers. This project demonstrates how to build custom MCP servers that can interact with Canvas educational platforms and provide enhanced functionality for educational workflows.

## Features
- **MCP Protocol Implementation**: Custom server following MCP specifications
- **Canvas Integration**: Direct interaction with Canvas LMS
- **Cloudflare Workers**: Serverless deployment with global edge distribution
- **Educational Tools**: Enhanced functionality for learning management
- **TypeScript Support**: Modern, type-safe development
- **Extensible Architecture**: Easy to customize and extend

## Technologies Used
- **TypeScript** - Type-safe development
- **Cloudflare Workers** - Serverless edge computing
- **MCP Protocol** - Model Context Protocol
- **Canvas API** - Educational platform integration
- **Modern JavaScript** - ES6+ features

## Quick Start

### Deploy to Cloudflare Workers
[![Deploy to Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/oskarcode/canvas-mcp-oskar)

This will deploy your MCP server to a URL like: `canvas-mcp-oskar.<your-account>.workers.dev/sse`

### Alternative: Local Setup
```bash
npm create cloudflare@latest -- my-canvas-mcp --template=oskarcode/canvas-mcp-oskar
```

## Configuration

### Environment Variables
Set up your Canvas API credentials:
```bash
CANVAS_API_URL=https://your-canvas-instance.instructure.com
CANVAS_API_TOKEN=your_canvas_api_token
```

### Customizing Your MCP Server
To add your own [tools](https://developers.cloudflare.com/agents/model-context-protocol/tools/) to the MCP server, define each tool inside the `init()` method of `src/index.ts` using `this.server.tool(...)`.

## Connect to Cloudflare AI Playground

You can connect to your MCP server from the Cloudflare AI Playground, which is a remote MCP client:

1. Go to https://playground.ai.cloudflare.com/
2. Enter your deployed MCP server URL (`canvas-mcp-oskar.<your-account>.workers.dev/sse`)
3. You can now use your Canvas MCP tools directly from the playground!

## Connect Claude Desktop to Your MCP Server

You can also connect to your remote MCP server from local MCP clients, by using the [mcp-remote proxy](https://www.npmjs.com/package/mcp-remote).

To connect to your MCP server from Claude Desktop, follow [Anthropic's Quickstart](https://modelcontextprotocol.io/quickstart/user) and within Claude Desktop go to Settings > Developer > Edit Config.

Update with this configuration:

```json
{
  "mcpServers": {
    "canvas-mcp": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://canvas-mcp-oskar.<your-account>.workers.dev/sse"
      ]
    }
  }
}
```

Restart Claude and you should see the Canvas tools become available.

## Canvas Integration Features

This MCP server provides tools for:
- **Course Management**: Access course information and content
- **Assignment Handling**: Create, update, and manage assignments
- **Student Data**: Access student enrollment and progress data
- **Grade Processing**: Handle grade calculations and submissions
- **Content Management**: Manage course materials and resources

## Development

### Local Development
```bash
npm install
npm run dev
```

### Building
```bash
npm run build
```

### Testing
```bash
npm test
```

### Deployment
```bash
npm run deploy
```

## MCP Protocol Features
This implementation supports:
- **Resource Discovery**: Find and access Canvas resources
- **Tool Execution**: Perform actions on Canvas data
- **Context Management**: Maintain educational context
- **Error Handling**: Robust error management
- **SSE Streaming**: Server-Sent Events for real-time communication

## Contributing
1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License
This project is open source and available under the [MIT License](LICENSE).

## Resources
- [Model Context Protocol Documentation](https://modelcontextprotocol.io/)
- [Canvas API Documentation](https://canvas.instructure.com/doc/api/)
- [Cloudflare Workers Documentation](https://developers.cloudflare.com/workers/)
- [TypeScript Documentation](https://www.typescriptlang.org/)

## Contact
- GitHub: [@oskarcode](https://github.com/oskarcode)
- Project Link: [https://github.com/oskarcode/canvas-mcp-oskar](https://github.com/oskarcode/canvas-mcp-oskar)

## Acknowledgments
- Model Context Protocol team for the specification
- Canvas for providing educational platform APIs
- Cloudflare for Workers platform
- The educational technology community

---
*Model Context Protocol implementation for Canvas integration on Cloudflare Workers*