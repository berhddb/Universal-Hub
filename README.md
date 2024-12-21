local ArrayField = loadstring(game:HttpGet('https://raw.githubusercontent.com/UI-Interface/ArrayField/main/Source.lua'))()
local UserInputService = game:GetService("UserInputService")

local Window = ArrayField:CreateWindow({
   Name = "Universal Hub",
   LoadingTitle = "Universal Hub",
   LoadingSubtitle = "V1.0",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "ArrayField"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key", -- It is recommended to use something unique as other scripts using ArrayField may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like ArrayField to get the key from
      Actions = {
            [1] = {
                Text = 'Click here to copy the key link <--',
                OnPress = function()
                    print('Pressed')
                end,
                }
            },
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

if UserInputService.KeyboardEnabled then
Window:Prompt({
    Title = 'AVISO!',
    SubTitle = 'Você é um usuário que usa PC.',
    Content = 'Caso o script não funcione, use outro executor. (Os scripts que irão aparecer serão somente os que tem suporte com seu dispositivo/PC)',
    Actions = {
        Close = {
            Name = 'Fechar Hub',
            Callback = function()
                ArrayField:Destroy()
            end,
        },
        Accept = {
            Name = 'Ok!',
            Callback = function()
                print('Pressed')
            end,
        }
    }
})
end

if UserInputService.TouchEnabled then
    Window:Prompt({
    Title = 'AVISO!',
    SubTitle = 'Você é um usuário que usa Celular.',
    Content = 'Caso o script não funcione, use outro executor. (Os scripts que irão aparecer serão somente os que tem suporte com seu dispositivo/Celular)',
    Actions = {
        Close = {
            Name = 'Fechar Hub',
            Callback = function()
                ArrayField:Destroy()
            end,
        }
    },
        Accept = {
            Name = 'Ok!',
            Callback = function()
                print('Pressed')
            end,
        }
})
end

local BloxFruitsTab = Window:CreateTab("Blox Fruits", nil)
local DoorsTab = Window:CreateTab("Doors", nil)
local AnimeVanguardTab = Window:CreateTab("Anime Vanguard", nil)
local FischTab = Window:CreateTab("Fisch", nil)
local BrookhavenTab = Window:CreateTab("Brookhaven", nil)
local BloxburgTab = Window:CreateTab("Bloxburg", nil)

if UserInputService.KeyboardEnabled then
local BloxFruitsSection = BloxFruitsTab:CreateSection("PC",true)

local GOGOHub = BloxFruitsTab:CreateButton({
   Name = "GOGO Hub",
   Interact = 'Execute',
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/berhddb/GOGOHub-Dragon-Update/refs/heads/main/README.md"))()
   ArrayField:Destroy()
   end,
})

local Kncrypt = BloxFruitsTab:CreateButton({
   Name = "Kncrypt",
   Interact = 'Execute',
   Callback = function()
   loadstring(game.HttpGet(game,'https://raw.githubusercontent.com/Yumiara/Python/refs/heads/main/BloxFruit-XYZ.lua'))()
   ArrayField:Destroy()
   end,
})
end

if UserInputService.TouchEnabled then
local BloxFruitsSection = BloxFruitsTab:CreateSection("Mobile",true)

local RedzHub = BloxFruitsTab:CreateButton({
   Name = "Redz Hub",
   Interact = 'Execute',
   Callback = function()
   -- loadstring(game.HttpGet(game,'https://raw.githubusercontent.com/Yumiara/Python/refs/heads/main/BloxFruit-XYZ.lua'))()
   -- ArrayField:Destroy()
   end,
})

local GOGOHub = BloxFruitsTab:CreateButton({
   Name = "GOGO Hub",
   Interact = 'Execute',
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/berhddb/GOGOHub-Dragon-Update/refs/heads/main/README.md"))()
   ArrayField:Destroy()
   end,
})
end
