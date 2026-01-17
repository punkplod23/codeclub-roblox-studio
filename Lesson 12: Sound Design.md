# 🔊 Lesson 12: Sound Design & Atmosphere
**Goal:** Make your game world come alive with background music and "3D sounds" that change based on where the player is standing!

---

### 🛠️ Step 1: Finding Sounds
Roblox has a massive library of sounds you can use for free.
1.  Open the **Toolbox** (View > Toolbox).
2.  Click the **Audio** tab (the small speaker icon).
3.  Search for "Ambient Music" or "Chill Beats."
4.  **Important:** Hover over a sound and click the "Copy Asset ID" button (it looks like a string of numbers).



---

### 💻 Step 2: Background Music (Ambient)
Ambient sound plays for everyone, no matter where they are on the map. It creates the "mood" of your game.

1.  In the **Explorer**, find the **SoundService** folder.
2.  Click the white **(+)** and add a **Sound**. Name it `BackgroundMusic`.
3.  In the **Properties** window:
    * Paste your copied ID into the **SoundId** box.
    * Check the box for **Playing**.
    * Check the box for **Looped** (so the song starts over when it ends).
    * Set the **Volume** to **0.5** (so it doesn't drown out the game).

---

### 💻 Step 3: 3D Sound (The Disco Ball)
3D sound is special because it gets louder as you walk toward the object and quieter as you walk away. 

1.  Find your **DiscoBall** from Lesson 10.
2.  Add a **Sound** directly inside the `DiscoBall` part. Name it `PartyMusic`.
3.  In the **Properties**:
    * Paste a dance music ID into **SoundId**.
    * Check **Playing** and **Looped**.
    * Find **RollOffMaxDistance**. Set this to **50**. This means once a player is 50 studs away, the music fades out completely!



---

### 📜 Step 4: Triggering Sounds with Code
You can also make sounds play only when a specific event happens, like a "Ka-ching!" when someone uses the shop.

Let's update your **Point Shop** from Lesson 11:
1.  Place a "Cash Register" sound inside your Shop Button.
2.  Update your `ShopScript` by adding these lines inside the "Success" section:

```lua
-- Add this inside the "if points.Value >= PRICE then" section
local sound = button:FindFirstChild("Sound")
if sound then
    sound:Play()
end
```

### 🧠 How it Works
- SoundService: This acts like a radio station for the whole server. Any sound here is "Global."
- Parenting to a Part: When a sound is placed inside a Part, Roblox automatically turns on Spatial Sound. It uses the player's camera position to decide if the sound should play in the left or right ear!
- RollOff: This determines the "hearing range." A small number means you have to be very close to hear it; a large number means it carries across the map.

### 🏆 Master Challenges
- The Spooky Forest: Can you make a "Trigger Zone" (an invisible part) that plays a scary sound only when a player walks through it? (Hint: Use Touched).
- The Low Health Heartbeat: Can you make a heartbeat sound play only when a player's health is below 20?
- Pitch Shifter: Click the (+) on your sound and add a PitchShiftSoundEffect. Can you use code to change the pitch based on the player's speed?
