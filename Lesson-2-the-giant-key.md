### 📝 Lesson 2: The Giant Key (Keyboard Input)

# ⌨️ Lesson 2: The "G" for Giant Key
**Goal:** Make your own character grow in size whenever you press a key on your keyboard!

### 🛠️ Step 1: Setup
1. In the **Explorer**, scroll down to the folder **StarterPlayer**.
2. Open it and find **StarterCharacterScripts**.
3. Click the **(+)** and add a **LocalScript**.

### 💻 Step 2: The Keyboard Code
```lua
local UserInputService = game:GetService("UserInputService")
local player = game.Players.LocalPlayer

-- This runs when you press a key
UserInputService.InputBegan:Connect(function(input, chat)
    if chat then return end -- Don't grow if you are just typing in chat!

    -- Check if the 'G' key was pressed
    if input.KeyCode == Enum.KeyCode.G then
        local character = player.Character
        local currentSize = character:GetScale()
        
        print("GROWING! 🦖")
        character:ScaleTo(currentSize + 0.2)
    end
end)
```
###🏆 Challenge: Can you make the "H" key make you tiny? (Hint: Use currentSize - 0.2)
