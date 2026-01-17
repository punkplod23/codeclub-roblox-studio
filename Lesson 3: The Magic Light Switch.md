# 💡 Lesson 3: The Magic Light Switch
**Goal:** Learn how to make a "toggle." This is a switch that remembers if a light is ON or OFF.

### 🛠️ Step 1: Setup
1. Create a **Part**, name it `Switch`, and make it look like a button.
2. Add a **ClickDetector** inside the Switch.
3. Create a second **Part** nearby, name it `Light`, and make the material **Neon**.
4. Add a **Script** inside the `Switch`.

### 💻 Step 2: The Logic Code
We are going to create a **Variable** called `isLightOn`. This is a piece of memory that can be either `true` or `false`.

```lua
local switch = script.Parent
local clickDetector = switch.ClickDetector
local lightPart = game.Workspace.Light

-- This is our "Memory" variable (it starts as true)
local isLightOn = true

clickDetector.MouseClick:Connect(function()
    if isLightOn == true then
        -- If it's on, turn it off!
        lightPart.Transparency = 1
        lightPart.CanCollide = false -- You can walk through it!
        isLightOn = false -- Tell the memory it's now OFF
        print("The light is now OFF")
    else
        -- If it's off, turn it back on!
        lightPart.Transparency = 0
        lightPart.CanCollide = true
        isLightOn = true -- Tell the memory it's now ON
        print("The light is now ON")
    end
end)
```

### 🏆 Master Challenges
The Sound of Light: Can you make the light turn Red when it's OFF and Green when it's ON?

The Disappearing Bridge: Rename your light "Bridge" and make it a long path. Now you’ve coded a bridge that you can turn on and off!
