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


### Send a Raw Message
```lua
game:GetService('TextChatService').TextChannels.RBXGeneral:SendSystemMessage('Message')
```


### When Message Received
```lua
game:GetService('TextChatService').MessageReceived:Connect(function(TextChatMessage)
    -- Function Here
end)
```




## LegacyChatService


### Send a Message as Player
```lua
game:GetService('ReplicatedStorage').DefaultChatSystemChatEvents.SayMessageRequest:FireServer('Message')
```

### Send a Whisper Message Player
```lua
game:GetService('ReplicatedStorage').DefaultChatSystemChatEvents.SayMessageRequest:FireServer('/w '..UserName..' Message', 'All')
```

### Send a Raw Message
```lua
game:GetService('StarterGui'):SetCore('ChatMakeSystemMessage', {
    Text = 'Message',
    Color = Color3.fromRGB(255, 255, 255),
    FontSize = 18,
    Font = Enum.Font.Arial
})
```

### When a Message in Chat is Filltered
```lua
game:GetService('ReplicatedStorage').DefaultChatSystemChatEvents.OnMessageDoneFiltering.OnClientEvent:Connect(function(Speaker, Channel)
    -- Function Here
end)
```
