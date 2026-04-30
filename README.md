# Sinister Library
Sinister Library is a Roblox CSGO-Styled UI Library created by me / @SinisterExploits on YouTube.
I never planned on releasing a video about this since it was meant to be private, but if you found this then congrats!

UI Toggle Keybind: RightShift

# Example Script
```
--// UI Settings \\--
local Theme = "Green"

--// Settings Applier \\--
local ThemeColor = Color3.fromRGB(244, 95, 115)
game:GetService("RunService").RenderStepped:Connect(function()
    if Theme == "Light Pink" or Theme == "Default" then
        ThemeColor = Color3.fromRGB(244, 95, 115)
    elseif Theme == "Yellow" or Theme == "Bright Yellow" then
        ThemeColor = Color3.fromRGB(255, 255, 0)
    elseif Theme == "White" then
        ThemeColor = Color3.fromRGB(255, 255, 255)
    elseif Theme == "Green" then
        ThemeColor = Color3.fromRGB(76, 153, 0)
    elseif Theme == "Cyan" then
        ThemeColor = Color3.fromRGB(0, 255, 255)
    elseif Theme == "Red" or Theme == "Dark Red" then
        ThemeColor = Color3.fromRGB(153, 0, 0)
    elseif Theme == "Blazed" then
        ThemeColor = Color3.fromRGB(232, 186, 200)
    elseif Theme == "Aura X" then
        ThemeColor = Color3.fromRGB(0, 0, 204)
    end
end)

--// Main Libraries \\--
local libary = loadstring(game:HttpGet("https://raw.githubusercontent.com/Sinister-Exploits/Sinister-Library/refs/heads/main/Source"))()
local Window = libary:new({name = "UI Name", accent = ThemeColor, textsize = 13})

--// Tabs \\--
local Tab1 = Window:page({name = "Tab1"})
local Tab2 = Window:page({name = "Tab2"})
local Tab3 = Window:page({name = "Tab3"})

--// Sections\\--
local Section1 = Tab1:section({name = "Section1", side = "left",size = 320})
local Section2 = Tab2:section({name = "Section2", side = "left",size = 320})
local Section3 = Tab3:section({name = "Section3", side = "right",size = 320})

local ConfigSection = Tab2:section({name = "Config",side = "right", size = 250})
local ConfigLoader = ConfigSection:configloader({folder = "ExampleScript"})

--// UI Elements \\--
Section1:toggle({name = "Toggle", def = false, callback = function(Boolean)
    print(Boolean)
end})

Section1:colorpicker({name = "Colorpicker", cpname = "", def = Color3.fromRGB(255, 255, 255), callback = function(color)
    print(color)
end})

Section1:dropdown({name = "Dropdown", def = "Option1", max = 3, options = {"Option1","Option2","Option3"}, callback = function(part)
    print(part)
end})

Section1:slider({name = "Slider", def = 50, max = 100, min = 0, rounding = true, callback = function(Value)
    print(Value)
end})

Section1:button({name = "Button", callback = function()
    print("Hello World")
end})

Section1:keybind({name = "Keybind", def = Enum.KeyCode.E, callback = function(Key)
    print(Key)
end})

--// UI Functions \\--
Tab1:openpage()
```

# Documents
Obviously I'll give the documents as a kind person.. lol

# Custom UI Settings (OPTIONAL)
I made this even though it was practically useless since you can just use your own colors for the UI accent.
Anyway put this at the top of the UI scripts:
```
--// UI Settings \\--
local Theme = "Light Pink"

--// Settings Applier \\--
local ThemeColor = Color3.fromRGB(244, 95, 115)
game:GetService("RunService").RenderStepped:Connect(function()
    if Theme == "Light Pink" or Theme == "Default" then
        ThemeColo--// UI Settings \\--
local Theme = "Aura X"

--// Settings Applier \\--
local ThemeColor = Color3.fromRGB(244, 95, 115)
game:GetService("RunService").RenderStepped:Connect(function()
    if Theme == "Light Pink" or Theme == "Default" then
        ThemeColor = Color3.fromRGB(244, 95, 115)
    elseif Theme == "Yellow" or Theme == "Bright Yellow" then
        ThemeColor = Color3.fromRGB(255, 255, 0)
    elseif Theme == "White" then
        ThemeColor = Color3.fromRGB(255, 255, 255)
    elseif Theme == "Green" then
        ThemeColor = Color3.fromRGB(76, 153, 0)
    elseif Theme == "Cyan" then
        ThemeColor = Color3.fromRGB(0, 255, 255)
    elseif Theme == "Red" or Theme == "Dark Red" then
        ThemeColor = Color3.fromRGB(153, 0, 0)
    elseif Theme == "Blazed" then
        ThemeColor = Color3.fromRGB(232, 186, 200)
    elseif Theme == "Aura X" then
        ThemeColor = Color3.fromRGB(0, 0, 204)
    end
end)
```

# Load Library
```
local libary = loadstring(game:HttpGet("https://raw.githubusercontent.com/Sinister-Exploits/Sinister-Library/refs/heads/main/Source"))()
```

# Create Window
```
local Window = libary:new({name = "UI Name", accent = ThemeColor, textsize = 13})
```

# Create Tabs
```
local Tab1 = Window:page({name = "Tab1"})
```

# Create Sections
```
local Section1 = Tab1:section({name = "Section1", side = "left",size = 320})
```

# Config Section (OPTIONAL)
```
local ConfigSection = Tab1:section({name = "Config",side = "left", size = 250})
local ConfigLoader = ConfigSection:configloader({folder = "ExampleScript"})
```

# Create Toggle
```
Section1:toggle({name = "Toggle", def = false, callback = function(Boolean)
    print(Boolean)
end})
```

# Create Button
```
Section1:button({name = "Button", callback = function()
    print("Hello World")
end})
```

# Config Slider
```
Section1:slider({name = "Slider", def = 50, max = 100, min = 0, rounding = true, callback = function(Value)
    print(Value)
end})
```

# Create Dropdown
```
Section1:dropdown({name = "Dropdown", def = "Option1", max = 3, options = {"Option1","Option2","Option3"}, callback = function(part)
    print(part)
end})
```

# Create Keybind
```
Section1:keybind({name = "Keybind", def = Enum.KeyCode.E, callback = function(Key)
    print(Key)
end})
```

# Create Colorpicker
```
Section1:colorpicker({name = "Colorpicker", cpname = "", def = Color3.fromRGB(255, 255, 255), callback = function(color)
    print(color)
end})
```

# Open Tab Function (OPTIONAL)
This is optional but I'd add this if I were you. If you put this in your script, it'll automatically open whatever tab selected.
Put this at the bottom of your script:
```
Tab1:openpage()
```

Thank you for using Sinister Library and please subscribe to my YouTube Channel:
https://www.youtube.com/@sinisterexploits****
