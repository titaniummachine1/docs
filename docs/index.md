# Home

The Lmaobox Lua API enables players and developers to enhance and expand their game by implementing their own ideas, features, visuals, and customizations.

## Community

If you want to contribute, share suggestions, report a problem, or report a bug, feel free to join the discussion on our
 [Discord](https://discord.gg/CwG7VkhSSm) and [Telegram group](https://t.me/+7LzWi43kypZjYWNk) 

 You can share and download Lua scripts on our [Forum](
 https://lmaobox.net/forum/v/categories/lua-scripts) 

## IDE

We recommend using [Visual Studio Code](https://code.visualstudio.com) with those extensions:

- [Lmaobox Lua Annotations](https://github.com/lnx00/Lmaobox-Annotations?tab=readme-ov-file) - static code analysis, type checking and autocompletion.

- [Lmaobox LUA snippets addon](https://marketplace.visualstudio.com/items?itemName=RC.lmaobox-lua-api-snippets) - autocompletion addon.

If you are using Open AI you can access API via [http://lmaobox.net/lua/sitemap.xml](http://lmaobox.net/lua/sitemap.xml)

### AI-Assisted Development (Local MCP)
If you are using an AI agent like Cursor, Claude Desktop, or Windsurf, you can provide it with the full Lmaobox API by installing a **community-maintained, third-party local MCP/context server**. This helps ensure the AI knows all current functions and constants with reduced hallucinations. This server is **not an official Lmaobox product or an officially supported component**.

**How to Install Locally (Community / Third-Party MCP Server):**
1. Clone or download the community MCP/context server repository (hosted under a personal GitHub account): https://github.com/titaniummachine1/Lmaobox_Context_Server
2. In your AI agent's MCP settings, add the local path to the cloned server repository.
3. Alternatively, tell your AI: "I have cloned a community Lmaobox MCP server to my machine. Please help me install it locally so you can access the API documentation." If automatic installation does not work, manually download/clone the repo yourself and then ask the AI to wire it up.
4. **Safety and support note:** This is a community/third-party project. Review the code and understand what it does before running it locally, and only run it in environments you trust. Maintenance, updates, and support for this server are provided by the community/author, not guaranteed by Lmaobox.

## Learning Lua

You can start learning Lua by following the friendly tutorial made by Garry's Mod developers: 

- [Garry's Mod Lua Tutorial](https://wiki.facepunch.com/gmod/Beginner_Tutorial_If_Then_Else)

Or any of the following guides for example:

- [Lua.org Tutorial](https://www.lua.org/pil/1.html)
- [Tutorialspoint Tutorial](https://www.tutorialspoint.com/lua/lua_overview.htm)

## How to start

1. Make sure you have Lmaobox loaded

2. Create example.lua file in your %localappdata%/lua/ folder and save your code there

3. Execute the script ingame using console command:

        lua_load example.lua

    Note it is also possible to execute lua code directly using:

        lua print( "Hello World" )


## Interaction overview diagram

![Screenshot](images/api.png)

## Top Examples

```lua title="FPS Counter - by x6h"
local consolas = draw.CreateFont("Consolas", 17, 500)
local current_fps = 0

local function watermark()
  draw.SetFont(consolas)
  draw.Color(255, 255, 255, 255)

  -- update fps every 100 frames
  if globals.FrameCount() % 100 == 0 then
    current_fps = math.floor(1 / globals.FrameTime())
  end

  draw.Text(5, 5, "[lmaobox | fps: " .. current_fps .. "]")
end

callbacks.Register("Draw", "draw", watermark)
-- https://github.com/x6h
```

```lua title="Damage logger - by @RC"
local function damageLogger(event)

    if (event:GetName() == 'player_hurt' ) then
        
        local localPlayer = entities.GetLocalPlayer();
        local victim = entities.GetByUserID(event:GetInt("userid"))
        local health = event:GetInt("health")
        local attacker = entities.GetByUserID(event:GetInt("attacker"))
        local damage = event:GetInt("damageamount")
        
        if (attacker == nil or localPlayer:GetIndex() ~= attacker:GetIndex()) then
            return
        end

        print("You hit " ..  victim:GetName() .. " or ID " .. victim:GetIndex() .. " for " .. damage .. "HP they now have " .. health .. "HP left")
    end

end

callbacks.Register("FireGameEvent", "exampledamageLogger", damageLogger)
-- Made by @RC
```

``` lua title="Basic player ESP"
local myfont = draw.CreateFont( "Verdana", 16, 800 )

local function doDraw()
    if engine.Con_IsVisible() or engine.IsGameUIVisible() then
        return
    end

    local players = entities.FindByClass("CTFPlayer")

    for i, p in ipairs( players ) do
        if p:IsAlive() and not p:IsDormant() then

            local screenPos = client.WorldToScreen( p:GetAbsOrigin() )
            if screenPos ~= nil then
                draw.SetFont( myfont )
                draw.Color( 255, 255, 255, 255 )
                draw.Text( screenPos[1], screenPos[2], p:GetName() )
            end
        end
    end
end
 
callbacks.Register("Draw", "mydraw", doDraw) 
```
