# 🌈 Lesson 8: Master of Light
**Goal:** Learn how to change the whole world's "vibe" using code and the Lighting service.

### 🛠️ Step 1: Setting the Scene
Before we code, we need to add the "Special Effects" to the game world.

1.  In your **Explorer** window, find the 💡 **Lighting** service.
2.  Click the white **(+)** button next to Lighting and add these three effects:
    * **BloomEffect** (This makes Neon parts look like they are glowing).
    * **ColorCorrectionEffect** (This lets you change the tint and brightness of the world).
    * **SunRaysEffect** (This adds beautiful "God rays" coming from the sun).

### 💻 Step 2: The Day/Night Switch
Let’s make a button that switches the game from **Day** to **Night** instantly!

1.  Open the **Baseplate** template.
2.  Create a **Part** (the Switch) and add a **ClickDetector** inside it.
3.  Add a **Script** inside the Part and type this:

```lua
local button = script.Parent
local clickDetector = button.ClickDetector
local lighting = game:GetService("Lighting")

local isNight = false

clickDetector.MouseClick:Connect(function()
	if isNight == false then
		-- 🌑 TURN TO NIGHT
		lighting.ClockTime = 0 -- 12:00 AM Midnight
		lighting.Brightness = 0
		lighting.OutdoorAmbient = Color3.fromRGB(0, 0, 50) -- Dark Blue sky tint
		
		isNight = true
		print("Night has fallen...")
	else
		-- ☀️ TURN TO DAY
		lighting.ClockTime = 14 -- 2:00 PM Afternoon
		lighting.Brightness = 3
		lighting.OutdoorAmbient = Color3.fromRGB(128, 128, 128) -- Normal light
		
		isNight = false
		print("The sun has risen!")
	end
end)
```

### 🎨 Step 3: Changing the "Vibe" (Color Correction)
You can use code to make the world look like a specific movie or environment. Try adding this to a button to change the colors:

```lua
local lighting = game:GetService("Lighting")
local colorEffect = lighting:FindFirstChild("ColorCorrectionEffect")

-- 🎬 Cinematic Black and White:
colorEffect.Saturation = -1 
colorEffect.TintColor = Color3.fromRGB(200, 200, 200)

-- ☢️ Radioactive Wasteland:
-- colorEffect.Saturation = 2
-- colorEffect.TintColor = Color3.fromRGB(0, 255, 0)
```

### 🧠 Why This is a "Pro Skill"
Professional Roblox builders use these settings to hide the "edge" of the map and make the game feel immersive.

- Bloom: Controls how much "glow" comes off neon parts.
- ClockTime: Ranges from 0 to 24. 12 is noon, 0 is midnight.
- Exposure: This is like a camera lens—it makes the whole world brighter or darker.

