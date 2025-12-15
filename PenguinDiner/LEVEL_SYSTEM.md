# Level System Documentation

## Overview

The Penguin Diner game now features a complete level system with 3 progressively challenging levels. Each level has specific goals, time limits, and difficulty parameters.

## Level Configuration

### Level 1
- **Time Limit**: 1 minute (~60 seconds)
- **Goal**: Serve 4 customers
- **Hearts**: 3
- **Tables**: 2
- **Max Active Customers**: 2
- **Pair Percentage**: 0% (no customer pairs)

### Level 2
- **Time Limit**: 2 minutes (~120 seconds)
- **Goal**: Serve 10 customers
- **Hearts**: 3
- **Tables**: 3
- **Max Active Customers**: 4
- **Pair Percentage**: ~30% (customer pairs appear frequently)

### Level 3
- **Time Limit**: 2 minutes (~120 seconds)
- **Goal**: Serve 13 customers
- **Hearts**: 3
- **Tables**: 3
- **Max Active Customers**: 6
- **Pair Percentage**: ~40% (customer pairs appear very frequently)

## Game Flow

1. **Level Start Screen**
   - Displays level number
   - Shows the goal (number of customers to serve)
   - Shows time limit
   - Shows number of hearts
   - Press ENTER to start the level

2. **Gameplay**
   - Timer counts down in real-time (displayed in seconds)
   - Hearts are lost when customers leave angry
   - Goal counter shows progress (Served/Goal)
   - Level ends when:
     - Goal is reached (Level Won!)
     - Time runs out (Level Failed)
     - All hearts are lost (Level Failed)

3. **Level Transitions**
   - Successfully completing a level advances to the next level
   - Failing a level shows a retry screen with options:
     - Press **R** to RETRY the same level
     - Press **Q** to QUIT the game
   - After completing all 3 levels, a victory screen is shown

4. **End Screens**
   - **Level Failed**: Shown when time runs out or hearts are depleted
     - Option to retry the level or quit
   - **Game Complete**: Shown after completing all 3 levels
   - **Game Over**: Shown when choosing to quit after failing

## Hearts System

- Each level starts with 3 hearts
- A heart is lost when a customer leaves angry (patience runs out)
- Hearts are displayed in the UI: "Hearts: 3"
- When hearts reach 0, the level is lost

## Timer System

- The timer counts down from the level's time limit
- Displayed as "Time: XXs" in the UI
- Timer only starts counting down after the player moves
- When time reaches 0, the level is lost

## Implementation Details

### Key Files

1. **LevelConfig.jack**: Contains configuration for all 3 levels
   - Stores level data in arrays
   - Provides getter methods for each level parameter

2. **Main.jack**: Manages level progression
   - Displays level start/end screens
   - Creates game instances for each level
   - Handles level transitions
   - Shows final game complete/game over screens

3. **PenguinDinerGame.jack**: Updated to support levels
   - Accepts level number and configuration
   - Implements timer countdown
   - Tracks hearts and handles heart loss
   - Returns boolean indicating level success/failure

### Customizing Levels

To modify level parameters, edit the `LevelConfig.jack` constructor:

```jack
// Example: Make Level 1 easier
let timeLimits[0] = 2000;  // Increase time to ~80 seconds
let goals[0] = 3;           // Reduce goal to 3 customers
```

To adjust pair spawn percentages, modify `pairThresholds`:
- Value 0 = 0% pairs
- Value 7 = ~30% pairs (with prime 23)
- Value 9 = ~40% pairs (with prime 23)
- Value 12 = ~50% pairs (with prime 23)

## Controls

- **Arrow Keys**: Move the penguin
- **Q**: Quit to menu (during gameplay)
- **Enter**: Start level (on level start screen)
- **R**: Retry level (on level failed screen)
- **Q**: Quit game (on level failed screen)
- **Any Key**: Exit (on game complete/game over screens)

## Tips for Players

1. **Level 1**: Focus on learning the mechanics. No pairs means simpler service.
2. **Level 2**: Manage time carefully. Customer pairs require serving two orders.
3. **Level 3**: Stay focused! With 6 active customers and 40% pairs, timing is crucial.

## Future Enhancements

Potential additions:
- More levels (easily add to LevelConfig arrays)
- Score tracking across levels
- Difficulty modes (easy/normal/hard)
- Bonus time for early completion
- Power-ups or special abilities
