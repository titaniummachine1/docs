## AI-Assisted Development

### API Reference (Web)
You can instruct your AI assistant to use the official Lmaobox Lua API docs:
- http://lmaobox.net/lua/sitemap.xml

### AI-Assisted Development (Recommended: Marketplace Extension)

For AI agents (VS Code, Cursor, Windsurf, Claude Desktop, etc.), use the community MCP extension:

- Marketplace: https://marketplace.visualstudio.com/items?itemName=titaniummachine1.lmaobox-context

This is the easiest path and is intended to be mostly zero-config.

#### Install Steps
1. Install **Lmaobox Context** from the VS Code Marketplace link above.
2. Reload your editor window.
3. Wait a few seconds for automatic setup.
4. If setup did not finish automatically, run:
   - `Lmaobox Context: Install Or Update Runtime`
5. If you use external MCP clients (Cursor/Windsurf/Claude/Desktop configs), run:
   - `Lmaobox Context: Sync External MCP Configs`

#### AI Prompt You Can Use
If needed, tell your AI assistant:

"I installed the Lmaobox Context extension from the Marketplace. Run setup by executing `Lmaobox Context: Install Or Update Runtime`, then `Lmaobox Context: Sync External MCP Configs`, and confirm Lmaobox tools are available."

### Manual/Legacy Option (Only If Needed)
If Marketplace install is unavailable, use the community repository:
- https://github.com/titaniummachine1/Lmaobox_Context_Server

### Safety and Support Note
This MCP/extension is a **community-maintained third-party project**.  
It is **not an official Lmaobox product** and is not officially supported by Lmaobox.  
Review code before running locally and only use it in environments you trust.
