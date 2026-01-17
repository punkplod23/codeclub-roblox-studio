# 🎨 Lesson 1: The Disco Dance Floor
**The Goal:** Learn how to use a **Loop** to make an object change colors forever.

### 🛠️ Step 1: Setup the Stage
1. Open **Roblox Studio** and start a new **Baseplate**.
2. Click the **Part** button at the top to drop a block into the game.
3. Use the **Scale** tool (at the top) to make the block big like a dance floor.
4. In the **Explorer** window on the right, hover over your Part and click the **(+)** button.
5. Search for **Script** and click it.

### 💻 Step 2: The Magic Code
Delete the "Hello World" text and type this exactly as shown:

```lua
local danceFloor = script.Parent 

-- This "while true do" loop runs forever!
while true do
    -- Pick a random color for the floor
    danceFloor.Color = Color3.new(math.random(), math.random(), math.random())
    
    -- This sends a message to the "Output" window
    print("The party is jumping! 🕺")
    
    -- This tells the script to wait 0.5 seconds before looping
    task.wait(0.5) 
end
```

Here are the two lessons formatted as separate Markdown files. You can copy the text inside each box and save them as Lesson1.md and Lesson2.md.

📝 Lesson 1: The Disco Dance Floor
Markdown

# 🎨 Lesson 1: The Disco Dance Floor
**The Goal:** Learn how to use a **Loop** to make an object change colors forever.

### 🛠️ Step 1: Setup the Stage
1. Open **Roblox Studio** and start a new **Baseplate**.
2. Click the **Part** button at the top to drop a block into the game.
3. Use the **Scale** tool (at the top) to make the block big like a dance floor.
4. In the **Explorer** window on the right, hover over your Part and click the **(+)** button.
5. Search for **Script** and click it.

### 💻 Step 2: The Magic Code
Delete the "Hello World" text and type this exactly as shown:

```lua
local danceFloor = script.Parent 

-- This "while true do" loop runs forever!
while true do
    -- Pick a random color for the floor
    danceFloor.Color = Color3.new(math.random(), math.random(), math.random())
    
    -- This sends a message to the "Output" window
    print("The party is jumping! 🕺")
    
    -- This tells the script to wait 0.5 seconds before looping
    task.wait(0.5) 
end

🏆 Master Challenges
Hyper-Speed: Can you change task.wait(0.5) to task.wait(0.1)?

Neon Glow: Click your floor part, look at the Properties window, and change the Material to Neon.

Secret Message: Change the text inside the print(" ") to say your name!
