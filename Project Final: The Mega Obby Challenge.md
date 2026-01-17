# 🎓 Final Project: The Mega Obby Challenge
**Goal:** Combine every skill you’ve learned to build a complete, playable "Obstacle Course" (Obby) game!

To pass the course, your game must include at least **one** element from every lesson. Check them off as you build!

---

### 🗺️ Level 1: The Basics (Lessons 1-3)
* [ ] **The Disco Floor:** Create a path of parts that change colors using a `while true do` loop.
* [ ] **The Growth Gate:** Create a door that only opens (or a part that grows) when clicked.
* [ ] **The Toggle Lights:** Use a light switch to brighten up a dark tunnel or room.

### 🏗️ Level 2: Physics & Hazards (Lessons 4-6)
* [ ] **The Disappearing Bridge:** Create a bridge that vanishes and reappears. Remember to **Anchor** your parts!
* [ ] **The Lava Pit:** Build a jumping puzzle over a red neon floor that resets the player's health to 0.
* [ ] **The Power-Up Sensor:** Create a "Magic Zone" that changes the player's color or size when they step into it.

### 📊 Level 3: The Economy (Lessons 7-9 & 11)
* [ ] **Leaderstats:** Ensure your "Points" show up in the top-right corner.
* [ ] **Coin Collection:** Scatter "Coins" throughout your course that add points when touched.
* [ ] **The Secret Portal:** Hide a portal that teleports players to a "Secret Winners Room."
* [ ] **The Point Shop:** Build a shop where players can spend points on **Super Speed** or **High Jump**.

### 🎆 Level 4: Atmosphere & Sound (Lessons 10 & 12)
* [ ] **Cinematic Lighting:** Use **ColorCorrection** or **Bloom** to make your game look unique.
* [ ] **Ambient Music:** Add a background track that plays for the whole game.
* [ ] **The Victory Disco:** Build a spinning Disco Ball in the "Winners Room" that plays 3D music and makes everyone dance!

---

### 💻 The Final Code: The "Win Pad"
At the very end of your course, place a **Win Pad**. This script rewards the player and sends them back to the start to play again!

```lua
local winPad = script.Parent

winPad.Touched:Connect(function(hit)
	local character = hit.Parent
	local player = game.Players:GetPlayerFromCharacter(character)
	
	if player then
		print(player.Name .. " Has Won the Game!")
		
		-- 1. Give them a massive "Win" bonus!
		player.leaderstats.Points.Value = player.leaderstats.Points.Value + 100
		
		-- 2. Play a victory sound
		local sound = winPad:FindFirstChildOfClass("Sound")
		if sound then 
            sound:Play() 
        end
		
		-- 3. Teleport them back to the start (SpawnLocation)
		local spawnLocation = game.Workspace:FindFirstChildOfClass("SpawnLocation")
		if spawnLocation then
			character:MoveTo(spawnLocation.Position)
		end
	end
end)
```

### 🚀 Graduation: Publishing Your Game
- Once you are finished, it's time to show the world!
- Go to File > Publish to Roblox.
- Give your game a cool name and description.
- Set the permissions to Public.
- Share the link with your friends and family so they can play your creation!

### Congratulations! You have completed the Code Club Roblox Module. You are now a Game Developer!
