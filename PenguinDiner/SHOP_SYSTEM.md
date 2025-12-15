# Shop System Documentation

## Overview

The Penguin Diner game now features a shop system where players can purchase upgrades between levels using the money they earn from serving customers.

## How It Works

### Money System

- **Score is now Money**: The game tracks money ($) instead of score points
- **Earning Money**: Collect payment from customers to earn money (tips based on patience)
- **Money Persists**: Money carries over between levels and even when retrying failed levels
- **Never Negative**: Money can't go below $0, even if customers leave angry

### Shop Access

The shop appears automatically:
1. **After completing a level** (before levels 2 and 3)
2. **Before retrying a failed level** (if player chose to retry)

Note: The shop does NOT appear after completing Level 3 (final level).

### Shop Interface

```
                    SHOP
              Money: $XX

    Use arrows to select, ENTER to buy

    [Speed Upgrade (+1 pixel)]        $10
    [Faster Cooking (-0.1 sec)]       $15
    [Extra Heart (next level)]        $20

          Press SPACE to continue
```

## Available Upgrades

### 1. Speed Upgrade - $10
- **Effect**: Increases penguin movement speed by +1 pixel per step
- **Base Speed**: 6 pixels per step
- **Stackable**: Yes (can buy multiple times)
- **Benefit**: Move faster around the restaurant to serve customers more efficiently

### 2. Faster Cooking - $15
- **Effect**: Reduces food preparation time by ~0.1 seconds (3 cycles)
- **Base Cooking Time**: 300 cycles (~12 seconds)
- **Stackable**: Yes (can buy multiple times)
- **Benefit**: Food is ready faster, reducing customer wait times

### 3. Extra Heart - $20
- **Effect**: Adds +1 heart for the NEXT level only
- **Base Hearts**: 3 per level
- **Stackable**: No (can only buy once per level)
- **Benefit**: Extra life protection against angry customers
- **Note**: Resets each level (not permanent)

## Shop Controls

- **Up/Down Arrows**: Navigate between shop items
- **Enter**: Purchase selected item (if you have enough money)
- **Space**: Exit shop and continue to next level

### Visual Feedback

- Selected item is **highlighted with a rectangle border**
- Money display updates immediately after each purchase
- Cannot purchase if insufficient funds (no error - just doesn't buy)

## Strategy Tips

### Early Game (Level 1)
- Focus on learning mechanics
- Try to earn as much money as possible
- Consider saving for cooking upgrade (most impactful)

### Mid Game (Level 2)
- Speed upgrade helps manage 4 active customers
- Cooking upgrade is crucial with customer pairs
- Extra heart provides safety net

### Late Game (Level 3)
- All upgrades are valuable with 6 active customers
- Stack speed upgrades to handle chaos
- Multiple cooking upgrades keep food flowing

## Implementation Details

### Key Classes

**Shop.jack**
- Manages shop UI and purchases
- Tracks total money and upgrades bought
- Handles item selection and purchasing
- Resets extra heart flag each level

**Main.jack**
- Shows level completion summary with money earned
- Creates and displays shop between levels
- Passes shop to game constructor for upgrade application

**PenguinDinerGame.jack**
- Uses money (not score) for payments
- Accepts Shop parameter in constructor
- Applies upgrades from shop

**GameConfig.jack**
- Stores speed upgrades in static variable
- Returns modified penguin speed based on upgrades

**Kitchen.jack**
- Accepts cooking upgrades
- Passes upgrades to FoodItem instances

**FoodItem.jack**
- Applies cooking time reduction based on upgrades
- Each upgrade reduces prep time by 3 cycles

## Money Flow

1. **Earning**: Serve customers → Collect payment → Earn money
2. **Tracking**: Money accumulates during level
3. **Summary**: Level end shows "Money earned: $X" and "Total money: $Y"
4. **Shopping**: Spend money on upgrades
5. **Carry Over**: Remaining money available for next level
6. **Retry**: Keep all money earned even when retrying failed levels

## Edge Cases Handled

- Can't buy with insufficient funds (silent fail)
- Can't buy Extra Heart twice in same shop visit (refunds automatically)
- Money never goes negative (floor at $0)
- Shop not shown after final level (Level 3)
- Shop shown before retrying failed levels
- Upgrades persist across level retries

## Upgrade Persistence

- **Speed Upgrades**: Permanent (stack across all levels)
- **Cooking Upgrades**: Permanent (stack across all levels)
- **Extra Heart**: Temporary (only for next level, then resets to base)

## Future Enhancements

Possible additions:
- More shop items (customer patience boost, auto-collect, etc.)
- Dynamic pricing (items get more expensive after purchase)
- Discount sales between certain levels
- Achievement-based bonuses
- Premium upgrades unlocked after beating game
