# 🕺 Lesson 10b: The Automatic Dance Floor
**Goal:** Make any player who gets close to the Disco Ball start dancing automatically using "Distance Math"!

---

### 🛠️ Step 1: The Dance Animation
Roblox has built-in "Emotes." To make a player dance, we need to tell the script which animation to play. We will use a classic dance ID: `rbxassetid://3333499508`.

### 💻 Step 2: The Proximity Script
We are going to use **Magnitude**. This is a math trick that tells the computer exactly how many "studs" (Roblox inches) away a player is from the ball.

1.  Open your **Disco Ball** from the previous lesson.
2.  Add a **new Script** inside the ball named `DanceScript`.
3.  Type this code:

```lua
local ball = script.Parent
local range = 15 -- How close the player needs to be (in studs)

-- This function makes the player dance
local function startDancing(humanoid)
	local anim = Instance.new("Animation")
	anim.AnimationId = "rbxassetid://3333499508" -- The Dance ID
	
	local loadAnim = humanoid:LoadAnimation(anim)
	loadAnim:Play()
end

while true do
	-- Look at every player currently in the game
	for _, player in pairs(game.Players:GetPlayers()) do
		local character = player.Character
		
		-- Make sure the player has a body (HumanoidRootPart)
		if character and character:FindFirstChild("HumanoidRootPart") then
			
			-- MATH MAGIC: Calculate the distance between Ball and Player
			local distance = (ball.Position - character.HumanoidRootPart.Position).Magnitude
			
			if distance < range then
				-- If they are close, check if they are already dancing
				local humanoid = character.Humanoid
				if not humanoid:FindFirstChild("IsDancing") then
					-- Add a "Tag" so we don't start the dance 100 times!
					local tag = Instance.new("BoolValue")
					tag.Name = "IsDancing"
					tag.Parent = humanoid
					
					startDancing(humanoid)
					print(player.Name .. " joined the party!")
				end
			end
		end
	end
	
	task.wait(1) -- Check for new dancers every second
end
```

### 🧠 How the "Magnitude" Logic Works
- .Magnitude: In the real world, we use a ruler. In code, we subtract the Player's position from the Ball's position. .Magnitude turns that into a simple number (like 10 feet).
- The "IsDancing" Tag: If we didn't use this, the script would try to start a new dance every second, making the player look like they are glitching. The "Tag" acts like a memory to say "This person is already busy dancing!"
- LoadAnimation: This "prepares" the dance moves so the player's character knows how to move their arms and legs.

### 🏆 Master Challenges
- The "Leave the Dancefloor" Fix: Can you add an else statement so that if the distance > range, the animation stops?
- Random Dances: Can you find a different Animation ID in the Roblox Library and make the ball pick a random dance for each person?
- Party Lights: Can you make the Disco Ball light get brighter when more people are nearby?
