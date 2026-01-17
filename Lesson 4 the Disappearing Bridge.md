# 🌉 Lesson 4: The Magic Bridge
**Goal:** Use a **Variable** to create a bridge that you can turn on and off. But be careful—if it's off, you'll fall through!

### 🛠️ Step 1: Build the Gap
1. Open the **Baseplate** template.
2. Create two big "Islands" using Parts (make them far apart so you have to jump).
3. Create a long, thin Part to be your **Bridge**. 
4. Move the bridge so it connects the two islands.
5. **CRUCIAL:** In the Properties window, make sure your Bridge is **Anchored** ⚓. (If it isn't, it will fall into the void when we turn off its collisions!)
6. Name the bridge part `MagicBridge`.
7. Create a small Part nearby to be your **Switch**. Add a **ClickDetector** inside it.
8. Add a **Script** inside the Switch.



### 💻 Step 2: The Bridge Logic
We are going to use a **Boolean** variable (True or False) to tell the bridge whether it should be "Solid" or "Ghostly."

```lua
local switch = script.Parent
local clickDetector = switch.ClickDetector
local bridge = game.Workspace.MagicBridge

-- This variable remembers if the bridge is working
local isBridgeActive = true

clickDetector.MouseClick:Connect(function()
	if isBridgeActive == true then
		-- TURN BRIDGE OFF (Ghost Mode)
		bridge.Transparency = 0.8  -- Make it see-through
		bridge.CanCollide = false  -- You will fall through it!
		bridge.Color = Color3.fromRGB(255, 0, 0) -- Turn it Red (Danger!)
		
		isBridgeActive = false
		print("The Bridge is GHOSTLY! Don't walk!")
	else
		-- TURN BRIDGE ON (Solid Mode)
		bridge.Transparency = 0    -- Make it solid
		bridge.CanCollide = true   -- You can walk on it!
		bridge.Color = Color3.fromRGB(0, 255, 0) -- Turn it Green (Safe!)
		
		isBridgeActive = true
		print("The Bridge is SOLID! Safe to cross.")
	end
end)
```

### 🏆 Master Challenges
The Trap Bridge: Can you make the bridge turn Invisible (Transparency = 1) when it is off so people don't know it's a trap?

The Material Change: Make the bridge Neon when it's active and Wood when it's off.

The Timer: Can you make the bridge stay on for 3 seconds and then turn off automatically? (Hint: Use task.wait(3)).
