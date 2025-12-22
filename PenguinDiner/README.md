# Penguin Diner Game - Nand2Tetris Project

A restaurant management game written in Jack language for the Nand2Tetris course! Run a bustling diner in Antarctica, serve penguin customers, and progress through increasingly challenging levels.

## Game Description

You play as a penguin waitress managing a busy diner. Customers arrive, sit at tables, order food, eat, and pay. Your job is to serve them efficiently before they lose patience and leave!

## 🎮 How to Play

### Controls
- **Arrow Keys** - Move your penguin around the restaurant
- **P** - Pause game
- **Q** - Quit to main menu

### Smart Auto-Actions
The game features intelligent **proximity-based actions** - simply move near customers or the kitchen and the appropriate action happens automatically!

**No need to press buttons for actions!** The game detects what you want to do:
1. **Near waiting customer** → Automatically seats them
2. **Near seated customer** → Automatically takes their order
3. **Near kitchen with ready food** → Automatically picks up food
4. **Near customer waiting for food (with food in hand)** → Automatically serves
5. **Near customer ready to pay** → Automatically collects payment

### Gameplay Flow

1. **Customers Arrive**: Penguin customers spawn in a queue on the left
2. **Seat Them**: Move near waiting customers to seat them at empty tables
3. **Take Orders**: Move near seated customers to take their food order
   - Orders appear as food icons at the kitchen
4. **Kitchen Prepares Food**: Watch the kitchen cook the meals (progress bars show)
5. **Pick Up Food**: Move near the kitchen when food is ready
   - You can carry 2 meals at once (one in each hand)!
6. **Serve Food**: Move near customers waiting for food to deliver their meals
7. **Customers Eat**: They'll eat for a few seconds (watch them enjoy!)
8. **Collect Payment**: A **$** symbol appears when they're done - collect to earn money!

### Customer Types

#### Solo Customers 🐧
- Order 1 meal
- Sit on left or right side of table
- Pay when finished eating

#### Pair Customers 🐧🐧
- Come in groups of 2
- Order 2 different meals
- Sit together at table center
- **Both must receive food** before they start eating
- **Both eat together** and finish at the same time
- Pay for both meals when done

### Patience System ⏰

Each customer has a **patience meter** that decreases over time:
- **Waiting in queue**: 45 seconds
- **Seated, waiting for order**: 20 seconds
- **Waiting for food**: 80 seconds
- **Eating**: Always completes (protected state)
- **Ready to pay**: 20 seconds

**If patience runs out, they leave angry and you lose a heart! ❤️**

## 🎯 Game Progression

### Levels (1-14)

The game has **4 main levels** by default, with **10 additional beta levels** available!

**Default Levels:**
- **Level 1**: 2 tables, 2 customers, 1 minute, 3 hearts
- **Level 2**: 3 tables, 3 customers, 3 minutes, 3 hearts
- **Level 3**: 4 tables, 4 customers, 4 minutes, 3 hearts
- **Level 4**: 4 tables, 5 customers, 4 minutes, 3 hearts

**Beta Levels (5-14):** Available by changing `GameConfig.getMaxLevel()` from 4 to 14!
- More tables (up to 6)
- More customers (up to 10)
- Longer time limits (up to 6 minutes)
- Fewer hearts (down to 1!)
- Higher pair spawn rates

### Level Goals

Each level has a **customer goal** - serve that many customers to win!
- You earn **money** for each customer served
- Money carries over between levels
- **Timer counts down** - complete the goal before time runs out!
- **Hearts** represent lives - lose all hearts and the level fails

### Winning & Losing

**Win Condition**: Serve the required number of customers before time runs out

**Lose Conditions**:
- Run out of time ⏰
- Lose all hearts ❤️ (from angry customers leaving)

**After Failing**: You can retry the level or quit to main menu

## 🛍️ The Shop System

Between levels, visit the **upgrade shop** to improve your abilities!

### Available Upgrades:

#### 1. Speed Upgrade (+0.5 pixel/move)
- **Prices**: $10, $15, $20, $25, $30...
- Makes your penguin move faster
- Stacks with each purchase!

#### 2. Faster Cooking (-0.3 seconds)
- **Prices**: $15, $20, $25, $30, $35...
- Reduces food preparation time
- Base time: 10.0 seconds
- Example: 3 upgrades = 9.0 second cooking time
- Stacks with each purchase!

#### 3. Extra Heart (Next Level Only)
- **Price**: $25 (constant)
- Gain +1 heart for the next level
- One-time use per level
- Great insurance for hard levels!

### Shop Controls:
- **Up/Down Arrows** - Select upgrade
- **Enter** - Purchase selected upgrade
- **Space** - Exit shop and start level

## 🍕 Food Types

The kitchen prepares **3 different meals**:
- **Pizza** 🍕
- **Burger** 🍔  
- **Ice Cream** 🍦

Each order is randomly assigned when a customer orders. Pairs get 2 different random meals!

## 🎨 Visual Elements

### Kitchen Display
- **Food slots** show cooking progress with progress bars
- **Ready indicator** appears when food is done
- Slots correspond to table numbers
- Kitchen at bottom-center of screen

### UI Display (Top of Screen)
- **Lv X** - Current level
- **Goal: X** - Customers needed to win
- **Served: X** - Customers served so far
- **$X** - Money earned this level
- **Hearts: X** - Remaining lives
- **Time: Xs** - Time remaining

### Customer States (Visual Cues)
- **Standing in queue** - Waiting to be seated
- **Sitting at table** - Waiting for order
- **Food icon above** - Waiting for food delivery
- **Eating animation** - Currently eating
- **$ symbol above** - Ready to pay!

## 📁 File Structure

### Core Game Files:
- `Main.jack` - Entry point, level progression, shop integration
- `PenguinDinerGame.jack` - Main game loop and logic
- `Penguin.jack` - Player character with food carrying
- `Customer.jack` - Customer AI with patience and states
- `Table.jack` - Restaurant tables with occupancy
- `Kitchen.jack` - Food preparation with cooking timers
- `FoodItem.jack` - Food graphics and rendering

### Configuration Files:
- `GameConfig.jack` - Game settings (speed, timing, **max level**)
- `LevelConfig.jack` - Level-specific settings (goals, tables, hearts)
- `ShopConfig.jack` - Shop prices for upgrades

### Documentation:
- `README.md` - This file

## 🔧 How to Compile and Run

### Method 1: Jack Compiler Script

```bash
# Navigate to PenguinDiner directory
cd PenguinDiner

# Compile all Jack files
JackCompiler.sh .
```

### Method 2: Nand2Tetris Tools

1. Open **JackCompiler** tool
2. Select the `PenguinDiner` directory
3. Click compile

### Running the Game:

1. Open **VMEmulator** tool
2. File → Load Program → Select `PenguinDiner` directory
3. Set **Animation** to "Fast" or "Fastest" for smooth gameplay
4. Click **Run** (or F5)

**Important**: The game runs better at faster animation speeds!

## 🎯 Strategy Tips

### General Tips:
1. **Seat customers immediately** - Don't let them wait in queue
2. **Take orders quickly** - The sooner you order, the sooner food cooks
3. **Pick up food as soon as ready** - Kitchen has limited slots
4. **Use both hands** - Carry 2 meals to serve faster
5. **Watch pair customers** - They need BOTH meals before eating
6. **Prioritize angry customers** - Low patience? Serve them first!
7. **Plan your path** - Minimize walking distance

### Advanced Strategies:
- **Pre-position near kitchen** when food is almost ready
- **Seat pairs at tables with short kitchen distance**
- **Group similar orders** to optimize trips
- **Buy speed upgrades first** - they help throughout the game
- **Save cooking upgrades** for later levels with more customers
- **Use extra hearts** on hard levels (6+)

### Level-Specific Tips:
- **Level 1-2**: Learn the mechanics, easy to pass
- **Level 3-4**: Start using upgrades, watch for pairs
- **Level 5+** (Beta): Speed is critical, plan efficient routes
- **Level 10+** (Beta): Expert mode - every second counts!

## ⚙️ Customization

### Enable Beta Levels (5-14):

1. Open `GameConfig.jack`
2. Find the `getMaxLevel()` function:
```jack
function int getMaxLevel() {
    return 4;  // Change this to 14!
}
```
3. Change `return 4;` to `return 14;`
4. Recompile the game
5. Enjoy 10 additional challenging levels!

### Other Customizable Settings:

**In GameConfig.jack:**
- `getGameLoopDelay()` - Game speed (lower = faster)
- `getBasePenguinSpeed()` - Player movement speed
- `getCustomerSpawnInterval()` - How often customers spawn
- `getPairThreshold()` - Percentage of pair customers
- Patience timers for each customer state
- Screen boundaries and positions

**In LevelConfig.jack:**
- Goals, tables, hearts, time limits for each level
- Pair spawn thresholds per level

**In ShopConfig.jack:**
- Upgrade prices for each tier

## 🐛 Known Behaviors

### Memory Management:
- All strings are manually created and disposed
- Proper object lifecycle management prevents memory leaks
- Optimized for Hack platform's limited heap (~14KB)

### Gameplay Notes:
- Customers in **eating state** (state 3) never leave angry - they always finish eating
- Only states 0,1,2,4 (player-dependent) can result in angry customers
- Pair customers are treated as a single entity until payment
- Kitchen has slots equal to number of tables
- Maximum 8 customers can exist at once (including queue)

### Graphics Limitations:
- Simple pixel art due to Hack platform constraints
- Text-based UI elements
- Basic animations

## 📊 Technical Details

- **Language**: Jack (Nand2Tetris)
- **Platform**: Hack Computer
- **Screen Resolution**: 512x256 pixels
- **Memory**: ~14KB heap
- **Architecture**: Object-oriented design
- **Libraries Used**: Screen, Keyboard, Output, Memory, Sys, String

### Class Architecture:
```
Main
├── PenguinDinerGame (game loop)
│   ├── Penguin (player)
│   │   └── FoodItem (food graphics)
│   ├── Customer[] (customer AI)
│   ├── Table[] (restaurant tables)
│   ├── Kitchen (food preparation)
│   │   └── FoodItem[] (cooking food)
│   ├── LevelConfig (level settings)
│   └── GameConfig (game settings)
├── Shop (upgrade system)
│   └── ShopConfig (shop prices)
└── LevelConfig (level data)
```

## 🎓 Educational Value

This project demonstrates:
- **Object-Oriented Programming** in Jack
- **Game loop architecture** with state management
- **Memory management** in constrained environments
- **Graphics programming** at the pixel level
- **AI behavior** with finite state machines
- **Collision detection** and proximity checks
- **User interface design** with limited resources

## 🏆 Credits

- **Course**: Nand2Tetris (nand2tetris.org)
- **Inspiration**: Classic Penguin Diner Flash game
- **Platform**: Hack Computer & VM Emulator
- **Language**: Jack Programming Language

## 🎮 Have Fun!

Serve your penguin customers efficiently, upgrade your abilities, and see if you can conquer all 14 levels! Good luck, and may your tips be generous! 🐧💰

---

*Pro tip: The secret to success is keeping all customers happy simultaneously. Master the art of multitasking!*
