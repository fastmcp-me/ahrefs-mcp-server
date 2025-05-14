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
1. Download Claude for Desktop
2. Select `Settings...`

<p align="center">
  <img src="images/claude1.png" alt="Open the Claude menu"/>
</p>

3. Click on `Developer` in the left panel, then `Edit Config`

<p align="center">
  <img src="images/claude2.png" alt="Open the MCP config file"/>
</p>

4. Paste the configuration [above](#configuration) into the open file

5. Restart the Claude app! If the installation is successful, it should look like this:

<p align="center">
  <img src="images/claude3.png" alt="ahrefs MCP appears under 'tools'"/>
</p>

If you prefer directly navigating to the file, the paths are:
- macOS: `~/Library/Application Support/Claude/claude_desktop_config.json`
- Windows: `%APPDATA%\Claude\claude_desktop_config.json`

If there are any issues, please refer to the [official documentation](https://modelcontextprotocol.io/quickstart/user)
#### Cursor
Cursor supports configurations that are either project-specific or global: the MCP configuration file will be at `.cursor/mcp.json` or `~/.cursor/mcp.json` respectively.
For more details, read the [official documentation](docs.cursor.com/context/model-context-protocol).
