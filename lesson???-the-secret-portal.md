# 🌀 Lesson 2: The Secret Portal
**The Goal:** Learn how to use an **Event** to move a player from one spot to another instantly.

### 🛠️ Step 1: Build the Gateways
1. Create **two** different Parts. 
2. Use the **Properties** window to name one `Entrance` and the other `Exit`.
3. **Important:** Make sure both parts have the **Anchored** checkbox checked so they don't fall!
4. Move the `Exit` part somewhere far away (or high in the sky!).
5. Add a **Script** inside the `Entrance` part.


### 💻 Step 2: The Portal Code
Delete the old code and type this:

```lua
local entrance = script.Parent
local destination = game.Workspace.Exit

-- This runs every time someone touches the Entrance
entrance.Touched:Connect(function(hit)
    
    -- Check if it's a character (player) that touched it
    local character = hit.Parent
    local isAPlayer = character:FindFirstChild("Humanoid")

    -- Only teleport if it's a real player!
    if isAPlayer then
        print("WOOSH! Portal Activated! 🚀")
        
        -- Move the character to the Exit's position
        -- We add 5 to the height (Y) so you land on top of the part!
        character:MoveTo(destination.Position + Vector3.new(0, 5, 0))
    end
end)
```

🏆 Master Challenges
- Invisibe Portal: Change the Transparency of the Entrance part to 1. Can you find it now?
- The Sound of Science: Add a print message inside the if statement that tells the player where they just landed.
- Colorful Travel: See if you can add a line inside the script to change the Entrance color every time someone touches it!
