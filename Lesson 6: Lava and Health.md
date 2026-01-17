# 🌋 Lesson 6: The Lava Floor
**Goal:** Learn how to make a part that "hurts" the player when they touch it.

### 🛠️ Step 1: Prepare the Baseplate
1. Open your **Baseplate** template in Roblox Studio.
2. Create a **Part**. 
3. Use the **Scale** tool to stretch it out into a big rectangle (a lava pit!).
4. Change its **Color** to Bright Red and its **Material** to **Neon** so it glows.
5. **CRITICAL:** In the Properties window, check the box for **Anchored** ⚓. If you don't, your lava might slide away!
6. Add a **Script** inside the lava part.



### 💻 Step 2: The Lava Code
We are going to use the **Sensor** logic from the last lesson, but this time we are going to change the player's **Health**.

```lua
local lava = script.Parent

-- This function runs when someone touches the lava
lava.Touched:Connect(function(hit)
	-- Look for the Character
	local character = hit.Parent
	
	-- Look for the "Humanoid" (The player's health bar)
	local humanoid = character:FindFirstChild("Humanoid")

	-- If we found a Humanoid, it means it's a player!
	if humanoid then
		print("🔥 OUCH! The lava is hot!")
		
		-- Setting health to 0 resets the player back to the start
		humanoid.Health = 0
	end
end)
```

### 🧠 How it Works: The Humanoid
Every player character in Roblox has a special object inside it called a Humanoid. The Humanoid controls:

Health: Usually 100. If it hits 0, the character resets.

WalkSpeed: How fast the player moves.

JumpHeight: How high the player can jump.

By coding humanoid.Health = 0, you are telling the game: "This player has run out of life!"

### 🏆 Master Challenges
Poison Floor: Change the code to humanoid.Health = humanoid.Health - 20. Now the player can touch the lava 5 times before they reset!

Healing Pad: Can you change the color to Green and make it humanoid.Health = 100? This creates a "Health Recharge" station.

Lava Sound: Add a "Sizzle" sound to the part and make it play when the player touches the lava.
