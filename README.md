# DracoAPI

A lightweight Roblox UI API for creating script hubs, testing tools, and custom interfaces.

> ⚠️ DracoAPI is currently in development.
>     Please do not deobfuscate the code as it will be open sourced once most features are added.

## Features

- Window creation
- Tabs
- Buttons
- Toggles
- Sections
- Notifications
- Customizable UI
- Designed for easy script-hub creation

## Getting Started

Load DracoAPI:

```lua
local DracoAPI = loadstring(game:HttpGet("YOUR_RAW_GITHUB_URL"))()
```

Create a window:

```lua
local Window = DracoAPI:CreateWindow({
    Name = "Draco Hub"
})
```

Create a tab:

```lua
local MainTab = Window:CreateTab({
    Name = "Main"
})
```

Create a button:

```lua
MainTab:CreateButton({
    Name = "Test Button",
    Callback = function()
        print("Button clicked!")
    end
})
```

Create a toggle:

```lua
MainTab:CreateToggle({
    Name = "Test Toggle",
    Default = false,

    Callback = function(Value)
        print("Toggle:", Value)
    end
})
```

## Example

```lua
local DracoAPI = loadstring(game:HttpGet("YOUR_RAW_GITHUB_URL"))()

local Window = DracoAPI:CreateWindow({
    Name = "Draco Hub"
})

local Main = Window:CreateTab({
    Name = "Main"
})

Main:CreateButton({
    Name = "Test",
    Callback = function()
        print("Hello from DracoAPI!")
    end
})

Main:CreateToggle({
    Name = "Example Toggle",
    Default = false,

    Callback = function(Value)
        print("Enabled:", Value)
    end
})
```

## API

### `CreateWindow()`

Creates the main DracoAPI window.

### `CreateTab()`

Creates a new tab/page inside the window.

### `CreateButton()`

Creates a clickable button.

### `CreateToggle()`

Creates an on/off toggle.

More functions will be added as DracoAPI develops.

## Development

DracoAPI is currently being developed and tested so there may be bugs.

The API may change while development continues.

## License

Free to use and modify.
