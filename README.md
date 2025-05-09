# Ahrefs MCP
A Model Context Protocol server to connect Claude desktop and other compatible AI assistants to Ahrefs.

## Installation
`npm` commands need to be executed in a terminal:
- macOS: open the Terminal from your Applications folder
- Windows: press Windows + R, type `cmd`, and press Enter
### Install Node.js and npm
1. Download Node.js from [nodejs.org](https://nodejs.org/en/download/)
2. Follow the installation instructions for your operating system
3. Verify installation by running:
```sh
npm -v
```
4. A version number will be printed if installation was successful
### Install Ahrefs MCP Server
```sh
npm install --prefix=~/.global-node-modules @ahrefs/mcp -g
```
### Upgrading versions
If you've installed our MCP server before, and just want to upgrade, run this command:
```sh
npm install --prefix=~/.global-node-modules @ahrefs/mcp@latest -g
```

## Configuration
You can now add the Ahrefs MCP to your favourite AI assistant app by adding the `ahrefs` part to your app's configuration file:
```json
{
    "mcpServers": {
        "ahrefs": {
            "command": "npx",
            "args": [
                "--prefix=~/.global-node-modules",
                "@ahrefs/mcp"
            ],
            "env": {
                "API_KEY": "YOUR_API_KEY_HERE"
            }
        }
    }
}
```
To learn more about creating or controlling API keys, refer to the [official documentation](https://docs.ahrefs.com/docs/api/reference/api-keys-creation-and-management).
### Where to find the configuration file
#### Claude Desktop
If you have not used any MCP servers before, please start by following the [official documentation](https://modelcontextprotocol.io/quickstart/user). 
You will then be able to find the MCP configuration file at:
- macOS: `~/Library/Application Support/Claude/claude_desktop_config.json`
- Windows: `%APPDATA%\Claude\claude_desktop_config.json`
#### Cursor
Cursor supports configurations that are either project-specific or global: the MCP configuration file will be at `.cursor/mcp.json` or `~/.cursor/mcp.json` respectively.
For more details, read the [official documentation](docs.cursor.com/context/model-context-protocol).
