🎨 Lesson 1: The Disco Dance Floor
The Goal: Learn how to use a Loop to make an object change colors forever.

🛠️ Setup
Open a new Baseplate in Roblox Studio.

Click Part at the top to drop a block into the game.

Use the Scale tool to make the block big enough to dance on.

In the Explorer window (on the right), hover over your Part and click the white (+) circle.

Select Script.

💻 The Code
Delete everything in the script and type this exactly:

Lua

local danceFloor = script.Parent 

-- This loop runs over and over again!
while true do
    -- Change the color to something random
    danceFloor.Color = Color3.new(math.random(), math.random(), math.random())
    
    -- Print a message in the Output window
    print("Party Mode: ON! 🕺")
    
    -- Wait half a second before changing again
    task.wait(0.5) 
end

🏆 Challenges
The Speedster: Change task.wait(0.5) to task.wait(0.1). How fast can you make it flash?

The Glow Up: Click your Part, go to the Properties window, and change the Material to Neon.
