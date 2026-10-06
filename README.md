# DracoAPI

A lightweight Roblox UI API for creating custom interfaces, script hubs, testing tools, and more.

> ⚠️ **DracoAPI Beta 0.1**
>
> DracoAPI is currently in public beta and under active development.
> Please do not deobfuscate or redistribute modified versions of the code while DracoAPI is under development. The project is planned to become open source once the majority of its features are complete.
>
> The API may change as development continues.

## Features

- Runtime-generated UI
- Windows
- Tabs
- Sections
- Buttons
- Toggles
- Sliders
- Text inputs
- Callback support
- Draggable windows
- Black and red default theme
- Multiple tabs and sections
- Designed for easy interface creation

## Getting Started

Load DracoAPI:

```lua
local DracoAPI = loadstring(game:HttpGet(
    "https://raw.githubusercontent.com/BlueFenster/DracoAPI/refs/heads/main/DracoAPI.main"
))()
```

Create a DracoAPI instance:

```lua
local Draco = DracoAPI.new()
```

Create a window:

```lua
local Window = Draco:CreateWindow({
    Name = "Draco Hub"
})
```

Create a tab:

```lua
local Main = Window:CreateTab({
    Name = "Main"
})
```

Create a section:

```lua
local Section = Main:CreateSection({
    Name = "Main Controls"
})
```

Create a button:

```lua
Section:CreateButton({
    Name = "Test Button",

    Callback = function()
        print("Button clicked!")
    end
})
```

Create a toggle:

```lua
Section:CreateToggle({
    Name = "Test Toggle",
    Default = false,

    Callback = function(Value)
        print("Toggle:", Value)
    end
})
```

Create a slider:

```lua
Section:CreateSlider({
    Name = "Power",
    Min = 0,
    Max = 100,
    Default = 50,

    Callback = function(Value)
        print("Power:", Value)
    end
})
```

Create an input:

```lua
Section:CreateInput({
    Placeholder = "Enter something...",

    Callback = function(Text)
        print("Input:", Text)
    end
})
```

## Full Example

```lua
local DracoAPI = loadstring(game:HttpGet(
    "https://raw.githubusercontent.com/BlueFenster/DracoAPI/refs/heads/main/DracoAPI.main"
))()

local Draco = DracoAPI.new()

local Window = Draco:CreateWindow({
    Name = "Draco Hub"
})

local Main = Window:CreateTab({
    Name = "Main"
})

local Section = Main:CreateSection({
    Name = "Controls"
})

Section:CreateButton({
    Name = "Test Button",

    Callback = function()
        print("Hello from DracoAPI!")
    end
})

Section:CreateToggle({
    Name = "Example Toggle",
    Default = false,

    Callback = function(Value)
        print("Enabled:", Value)
    end
})

Section:CreateSlider({
    Name = "Power",
    Min = 0,
    Max = 100,
    Default = 50,

    Callback = function(Value)
        print("Power:", Value)
    end
})

Section:CreateInput({
    Placeholder = "Type something...",

    Callback = function(Text)
        print("Entered:", Text)
    end
})
```

## API

### `DracoAPI.new()`

Creates a new DracoAPI instance.

```lua
local Draco = DracoAPI.new()
```

### `Draco:CreateWindow()`

Creates the main DracoAPI window.

```lua
local Window = Draco:CreateWindow({
    Name = "My Window"
})
```

### `Window:CreateTab()`

Creates a new tab inside the window.

```lua
local Tab = Window:CreateTab({
    Name = "Main"
})
```

### `Tab:CreateSection()`

Creates a section inside a tab.

```lua
local Section = Tab:CreateSection({
    Name = "Controls"
})
```

### `Section:CreateButton()`

Creates a clickable button.

```lua
Section:CreateButton({
    Name = "Test",

    Callback = function()
        print("Clicked")
    end
})
```

### `Section:CreateToggle()`

Creates an on/off toggle.

```lua
Section:CreateToggle({
    Name = "Enabled",
    Default = false,

    Callback = function(Value)
        print(Value)
    end
})
```

### `Section:CreateSlider()`

Creates a slider.

```lua
Section:CreateSlider({
    Name = "Power",
    Min = 0,
    Max = 100,
    Default = 50,

    Callback = function(Value)
        print(Value)
    end
})
```

### `Section:CreateInput()`

Creates a text input.

```lua
Section:CreateInput({
    Placeholder = "Enter text...",

    Callback = function(Text)
        print(Text)
    end
})
```

## Element Controls

Some elements return an object that can be controlled after creation.

### Toggle

```lua
local Toggle = Section:CreateToggle({
    Name = "Example",
    Default = false
})

Toggle:Set(true)

print(Toggle:Get())
```

### Slider

```lua
local Slider = Section:CreateSlider({
    Name = "Power",
    Min = 0,
    Max = 100,
    Default = 50
})

Slider:Set(100)

print(Slider:Get())
```

## Development

DracoAPI is currently in **Beta 0.1**.

The framework has been tested with:

- Multiple windows
- Multiple tabs
- Multiple sections
- Multiple buttons
- Multiple toggles
- Multiple sliders
- Multiple inputs
- Dynamic element creation
- Element state controls
- Tab switching
- UI dragging

Bugs and API changes are expected while development continues.

New elements, customization options, themes, and other features will be added in future releases.

## Roadmap

Planned features include:

- Dropdowns
- Keybinds
- Notifications
- Theme customization
- More UI elements
- Improved mobile support
- Better documentation
- Additional configuration options

## License

Free to use and modify.

DracoAPI is currently under development and is planned to become open source once the majority of its features are complete.
