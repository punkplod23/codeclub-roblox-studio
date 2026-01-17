# 🪩 Lesson 10: The Ultimate Disco Ball
**Goal:** Create a rotating disco ball that changes the color of the whole room using random math and light objects!

---

### 🛠️ Step 1: Building the Ball
To make a disco ball, we need a shiny shape and a light source that "beams" out into the room.

1.  Open your **Baseplate** template in Roblox Studio.
2.  Create a **Sphere** part and name it `DiscoBall`.
3.  Place it high in the air and make sure it is **Anchored** ⚓ in the Properties window.
4.  Change its material to **Foil** (for a mirrored look) or **Neon** (for a glow look).
5.  **The Secret Ingredient:** Inside the `DiscoBall` in the Explorer, click the white **(+)** and add a **PointLight**. 



> **Pro Tip:** In the **Properties** window for the PointLight, set the `Brightness` to **10** and the `Range` to **30**. This ensures the light hits the walls and floor!

---

### 💻 Step 2: The Disco Script
We want the ball to do two things at once: **Spin** like a motor and **Flash colors** like a strobe light.

1.  Add a **Script** inside your `DiscoBall`.
2.  Delete the "Hello World" text and type this:

```lua
local ball = script.Parent
local light = ball:FindFirstChildOfClass("PointLight")

-- This loop runs forever!
while true do
	-- 1. Create a random color using the "Rainbow Wheel" (HSV)
	local randomColor = Color3.fromHSV(math.random(), 1, 1)
	
	-- 2. Apply the color to the ball AND the light
	ball.Color = randomColor
	if light then
		light.Color = randomColor
	end
	
	-- 3. Make the ball spin a little bit using CFrame
	-- CFrame.Angles uses "radians," so we use math.rad to turn 10 degrees
	ball.CFrame = ball.CFrame * CFrame.Angles(0, math.rad(10), 0)
	
	-- 4. Wait a tiny bit before the next flash
	task.wait(0.1) 
end
```

### 🧠 How the Logic Works
- Color3.fromHSV: Instead of picking specific Red/Green/Blue numbers, HSV (Hue, Saturation, Value) lets the computer pick a random spot on the "Rainbow Wheel." math.random() picks a decimal between 0 and 1, which selects the color.
- CFrame.Angles: This is how we tell a part to rotate. Unlike Orientation, using CFrame inside a loop makes the rotation look smooth and professional.
- task.wait(0.1): This is the "BPM" (Beats Per Minute) of your disco.
-- Change it to 0.5 for a slow, chill vibe.

-- Change it to 0.02 for a high-energy rave!

### 🏆 Master Challenges
- The Rainbow Floor: Can you create a "Dance Floor" out of many parts and use a loop to make them all change colors at the same time as the ball?
- The Sound of Music: Add a Sound object to the ball. In your script, add ball.Sound:Play() at the very top (before the loop) so the party has music!
- Toggle Switch: Can you combine this with Lesson 3 (The Magic Light Switch)? Make the disco ball stay off until a player clicks a "Party Button."
