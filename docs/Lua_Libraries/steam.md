# steam

The steam library provides access to basic Steam API functionality and data.

## Functions

### GetSteamID()

Returns SteamID of the user as string.

### GetPlayerName( steamid: string )

Returns the player name of the player having the given SteamID.

### IsFriend( steamid: string )

Returns true if the player is a friend of the user.

### GetFriends()

Returns a table of all friends of the user.

### ToSteamID64( steamid: string )

Returns the 64bit SteamID of the player as a long integer.

## Examples

```lua title="Get Names"
---@param lobby GameServerLobby
local function OnLobbyUpdated( lobby )
	local members = lobby:GetMembers()
	for _, player in pairs(members) do
		local steamID = player:GetSteamID()
		local name = steam.GetPlayerName(steamID)
		print(name)
	end
end

callbacks.Register("OnLobbyUpdated", OnLobbyUpdated)
```