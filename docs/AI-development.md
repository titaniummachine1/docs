# AI-Assisted Development 

## AI Chats And Agents

You can insruct your AI assistant to read about our API via link [http://lmaobox.net/lua/sitemap.xml](http://lmaobox.net/lua/sitemap.xml)

## AI-Assisted Development (Local MCP)

If you are using an AI agent like Cursor, Claude Desktop, or Windsurf, you can provide it with the full Lmaobox API by installing a **community-maintained, third-party local MCP/context server**.

This helps ensure the AI knows all current functions and constants with reduced hallucinations. This server is **not an official Lmaobox product or an officially supported component**.

**How to Install Locally (Community / Third-Party MCP Server):**

1. Clone or download the community MCP/context server repository (hosted under a personal GitHub account): [https://github.com/titaniummachine1/Lmaobox_Context_Server](https://github.com/titaniummachine1/Lmaobox_Context_Server)

2. In your AI agent's MCP settings, add the local path to the cloned server repository.

3. Alternatively, tell your AI: "I have cloned a community Lmaobox MCP server to my machine. Please help me install it locally so you can access the API documentation." 
    If automatic installation does not work, manually download/clone the repo yourself and then ask the AI to wire it up.

**Safety and support note:** This is a community/third-party project. Review the code and understand what it does before running it locally, and only run it in environments you trust. Maintenance, updates, and support for this server are provided by the community/author, not guaranteed by Lmaobox.