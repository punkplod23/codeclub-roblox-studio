# 🏆 Lesson 7: The Leaderboard (Tracking Points)
**Goal:** Create a list in the top-right corner of the screen that tracks how many "Points" or "Wins" a player has!

---

### 🛠️ Step 1: Where the Script Goes
This script is special. It doesn't live inside a part; it runs for the whole game the moment someone joins.

1.  Open your **Baseplate** template in Roblox Studio.
2.  In the **Explorer** window, find the folder called **ServerScriptService**.
3.  Click the white **(+)** and add a **Script**. 
4.  Rename this script to `LeaderboardScript`.


### 💻 Step 2: The Leaderstats Code
Type this exactly as shown. Roblox is very picky—it looks for the specific name `"leaderstats"` (all lowercase) to make the menu appear!

```lua
game.Players.PlayerAdded:Connect(function(player)
	-- 1. Create a folder inside the player to hold their stats
	local stats = Instance.new("Folder")
	stats.Name = "leaderstats" -- MUST be lowercase!
	stats.Parent = player

	-- 2. Create a "Points" value
	local points = Instance.new("IntValue")
	points.Name = "Points" -- This is the name that shows up in the menu!
	points.Value = 0       -- Everyone starts at zero
	points.Parent = stats
end)```


### 💰 Step 3: Making a "Point Collector"
Now that we have a leaderboard, we need a way to earn points!

1. Create a Part (make it look like a gold coin or a star).
2. Anchor it ⚓ so it stays floating in the air.
3. Add a Script inside the coin and type this:

```lua
local coin = script.Parent

coin.Touched:Connect(function(hit)
	local character = hit.Parent
	local player = game.Players:GetPlayerFromCharacter(character)

	-- Check if a real player (not a random brick) touched it
	if player then
		-- Add 1 to their "Points" on the leaderboard
		player.leaderstats.Points.Value = player.leaderstats.Points.Value + 1
		
		-- Make the coin disappear so they can't grab it again!
		coin:Destroy() 
		print("Point Awarded to " .. player.Name)
	end
end)```

### How it Works
- PlayerAdded: This is an event that waits for a person to join the game. The script then "gives" them a folder of stats.
- IntValue: This stands for Integer Value. An "integer" is just a fancy math word for a whole number (like 1, 5, or 100).
- GetPlayerFromCharacter: Remember, when you touch a part, only your foot or hand touches it. This line of code helps the computer figure out which player that foot belongs to so it knows who to give the points to!

### 🏆 Master Challenges
- The High Roller: Can you make a "Mega Coin" that gives the player 50 points?
- The Lava Penalty: Can you go back to your Lava Script (Lesson 5) and make it subtract 5 points if they touch the lava? (Hint: Points.Value = Points.Value - 5).
- Multi-Stats: Can you add a second value to the leaderboard called "Wins"? (Copy the points section of the code and change the name to "Wins").
