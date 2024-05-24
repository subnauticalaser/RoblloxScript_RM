# Roblox Chat

## TextChatService

### Send a Message as Player
```lua
game:GetService('TextChatService').ChatInputBarConfiguration.TargetTextChannel:SendAsync('Message')
```

### Send a Whisper Message as Player
```lua
local oldChannel = game:GetService('TextChatService').ChatInputBarConfiguration.TargetTextChannel
local newChannel = cloneref(game:GetService('RobloxReplicatedStorage')).ExperienceChat.WhisperChat:InvokeServer(UserId)

if newChannel then
    newChannel:SendAsync('Message')
end

game:GetService('TextChatService').ChatInputBarConfiguration.TargetTextChannel = oldChannel
```
