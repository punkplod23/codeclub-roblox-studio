# 🛒 Lesson 11: The Point Shop
**Goal:** Create a shop button that checks a player's **Leaderstats** and lets them "spend" their points to buy a Super Speed boost!

### 🛠️ Step 1: Building the Shop Pedestal
1.  Create a **Part** to be your shop button or pedestal. 
2.  Add a **ClickDetector** inside the Part.
3.  Add a **Script** inside the Part and name it `ShopScript`.
4.  **Optional:** To make it look professional, add a **BillboardGui** with a **TextLabel** on top of the part that says: *"Super Speed: 10 Points"*.

### 💻 Step 2: The Purchase Logic
This script acts as the "Gatekeeper." It checks if the player is rich enough to buy the item. If they have enough points, it subtracts the cost and gives them the reward!

```lua
local button = script.Parent
local clickDetector = button.ClickDetector

-- 1. Set the price and the reward amount
local PRICE = 10 
local NEW_SPEED = 50 -- The default speed is 16

clickDetector.MouseClick:Connect(function(player)
	-- 2. Find the player's points (from the leaderstats we made in Lesson 7)
	local points = player:FindFirstChild("leaderstats") and player.leaderstats:FindFirstChild("Points")
	
	if points then
		-- 3. Check if they have enough money!
		if points.Value >= PRICE then
			-- SUCCESS! Subtract the points
			points.Value = points.Value - PRICE
			print(player.Name .. " bought Super Speed!")
			
			-- 4. Apply the reward to the Player's Humanoid
			local character = player.Character
			if character and character:FindFirstChild("Humanoid") then
				character.Humanoid.WalkSpeed = NEW_SPEED
				
				-- Let's make their feet glow so people know they bought a power-up!
				button.Color = Color3.fromRGB(0, 255, 0) -- Turn button Green for success
				task.wait(1)
				button.Color = Color3.fromRGB(163, 162, 165) -- Turn back to grey
			end
		else
			-- FAILURE! Tell them they need more points
			print("You need " .. (PRICE - points.Value) .. " more points!")
			button.Color = Color3.fromRGB(255, 0, 0) -- Turn button Red for fail
			task.wait(1)
			button.Color = Color3.fromRGB(163, 162, 165)
		end
	end
end)
```

### 🧠 How the Logic Works
- The Comparison (>=): This stands for "Greater than or Equal to." It is the most important part of shop code! It prevents players from spending points they don't have.
- The Subtraction: points.Value = points.Value - PRICE updates the leaderboard immediately. The player will see their "Points" number go down in the top-right corner.
- The WalkSpeed Property: Every player starts with a speed of 16. By changing this number in the Humanoid, you change how fast the character's legs move!

### 🏆 Master Challenges
- The Gravity Shop: Instead of speed, can you make a button that changes humanoid.JumpHeight to 100?
- The Sound of Success: Find a "Cash Register" sound in the Toolbox. Add it to the button and use button.Sound:Play() only when the purchase is successful.
- The Rainbow Trail: Can you make the player leave a trail of colors behind them once they buy the speed boost?
