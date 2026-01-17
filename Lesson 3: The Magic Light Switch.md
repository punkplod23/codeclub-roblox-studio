# 💡 Lesson 3: The Magic Light Switch
**Goal:** Learn how to make a "toggle." This is a switch that remembers if a light is ON or OFF.

### 🛠️ Step 1: Setup
1. Open Roblox Studio and start a new Baseplate.
2. Create a **Part**, name it `Switch`, and make it look like a button.
3. Add a **ClickDetector** inside the Switch.
4. Create a second **Part** nearby, name it `Light`, and make the material **Neon**.
5. Add a **Script** inside the `Switch`.

### 💻 Step 2: The Logic Code
We are going to create a **Variable** called `isLightOn`. This is a piece of memory that can be either `true` or `false`.

```lua
local switch = script.Parent
local clickDetector = switch.ClickDetector
local lightPart = game.Workspace.Light

local isLightOn = true

clickDetector.MouseClick:Connect(function()
	if isLightOn == true then
		-- TURN OFF
		lightPart.Transparency = 0.8 -- Ghostly invisible
		lightPart.Material = Enum.Material.Plastic -- Remove the glow
		lightPart.Color = Color3.fromRGB(50, 50, 50) -- Make it dark grey

		isLightOn = false
		print("The light is now OFF")
	else
		-- TURN ON
		lightPart.Transparency = 0 -- Fully solid
		lightPart.Material = Enum.Material.Neon -- Make it glow!
		lightPart.Color = Color3.fromRGB(255, 255, 0) -- Bright Yellow

		isLightOn = true
		print("The light is now ON")
	end
end)
```

### 🏆 Master Challenges
The Sound of Light: Can you make the light turn Red when it's OFF and Green when it's ON?
