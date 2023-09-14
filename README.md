# XVE UI Library
![Screenshot 2023-09-11 200814](https://github.com/3345-c-a-t-s-u-s/XVE-UI-Lib/assets/117000269/e0af566c-9977-48d0-9d82-db40971d3238)
![Screenshot 2023-09-14 164949](https://github.com/3345-c-a-t-s-u-s/XVE-UI-Lib/assets/117000269/2e4428d0-36b7-4bec-8fa1-f164395a466e)

## [Source](https://raw.githubusercontent.com/3345-c-a-t-s-u-s/XVE-UI-Lib/main/source)

# Example Source
```lua
local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/3345-c-a-t-s-u-s/XVE-UI-Lib/main/source"))()

local Window = library:Window("XVE UI")
local Notification = library:Notification()
local Watermark = Window:Watermark()

local WaterPING = Watermark:NewWatermark("PING: ")

coroutine.wrap(function()
	while true do task.wait(0.1)
		WaterPING:Text(tostring("PING: ")..tostring(math.ceil(game:GetService('Workspace'):GetServerTimeNow())))
	end
end)()

Window:AddToggleButton()
Window:SetKeybindToggle(Enum.KeyCode.X)

local ExampleTab = Window:Tab("Example Tab")

ExampleTab:NewLabel("Example Tab")
ExampleTab:Layout()

ExampleTab:NewButton("Button",function()
	print('button')
end)

ExampleTab:NewButton("Notification",function()
	Notification:Notify("Notification",3)
end)

ExampleTab:NewToggle("Toggle",false,function(val)
	print("toggle",val)
end)

ExampleTab:NewKeybind("Keybind",nil,function(val)
	print("bind",val)
end)

ExampleTab:NewTextBox("Textbox","Input",function(val)
	print("Textbox",val)
end)

ExampleTab:NewSlider("Slider",{Min=1,Max=100,Default=5},function(val)
	print("slider",val)
end)

ExampleTab:NewDropdown("dropdown",{1,2,3},1,function(val)
	print('dropdown',val)
end)
```
