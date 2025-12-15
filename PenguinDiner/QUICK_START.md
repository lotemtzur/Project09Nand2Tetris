# 🐧 PENGUIN DINER - Quick Start Guide

## ⚡ Running Faster Than "Fast"

Unfortunately, the VM Emulator only has two speeds: "Slow" and "Fast". However, here are tips to make the game run better:

### Option 1: Use "Fast" Mode (Recommended)
1. Open VM Emulator
2. Load Program → Select PenguinDiner directory
3. Click the **"Fast"** button in the toolbar
4. Click **"Run"**

### Option 2: For Even Faster Execution
The game will initialize in about 30-60 seconds on "Fast" mode. The initialization time is due to:
- Drawing 4 detailed tables with 3D effects
- Drawing the penguin with detailed graphics
- Setting up the game state

**This is normal for Jack/VM programs with graphics!**

## 🎮 How to Know the Game Has Started

### Clear "READY TO PLAY!" Message
After initialization completes, you will see:

```
*** READY TO PLAY! ***
Use ARROW KEYS to move penguin!
```

This message appears in the **center of the screen** (around row 10-11).

### Game is Ready When:
1. ✅ You see **"*** READY TO PLAY! ***"** message
2. ✅ You see your **penguin** in the center (larger penguin with belly)
3. ✅ You see **4 tables** (circles with legs at the corners)
4. ✅ **Arrow keys work** - try moving your penguin!
5. ✅ **First customer spawns** in ~5 seconds at left side with **!** mark

## 🎯 First Steps After "READY TO PLAY!"

1. **Test Movement**
   - Press **Arrow Keys** to move your penguin
   - You should see the penguin move around the screen

2. **Wait for Customer** (~5 seconds)
   - A small penguin will appear at the **left side** (x=30, y=120)
   - Look for the **! exclamation mark** above the customer

3. **Start Playing!**
   - Move to the customer with Arrow Keys
   - Press **S** to seat them at a table
   - Follow the workflow: Seat → Order → Serve → Collect

## ⏱️ Customer Spawning

- **First customer**: Spawns ~5 seconds after game starts
- **Next customers**: Every ~5-8 seconds after that
- **Maximum**: 4 customers (one per table)
- **Location**: Always at left entrance (x=30, y=120)
- **Indicator**: Look for the **!** exclamation mark

## 🐛 Troubleshooting

### "Penguin Not Moving"
- Make sure the **"READY TO PLAY!"** message appeared
- Make sure you're using **Arrow Keys** (↑ ↓ ← →)
- Try pressing and releasing the arrow key (don't hold too long)
- If still stuck, the game may still be initializing - wait 30 more seconds

### "No Customers Coming"
- Wait at least **10 seconds** after "READY TO PLAY!" appears
- Look at the **left side** of the screen (x=30, y=120)
- Customers spawn every ~5-8 seconds
- If all 4 tables are occupied, no more customers will spawn until you serve and collect from existing ones

### "Game Takes Too Long to Start"
- This is normal for Jack programs with graphics
- On "Fast" mode, expect 30-60 seconds initialization
- You'll know it's done when you see "*** READY TO PLAY! ***"
- The detailed graphics (penguin, tables with 3D effects) take time to draw

## 📊 What You Should See Initially

```
┌─────────────────────────────────────────┐
│ PENGUIN DINER          Score: 0         │
│ Controls: Arrows=Move, S=Seat...        │
├─────────────────────────────────────────┤
│                                          │
│     [Table]         [Table]             │
│        O               O                 │
│                                          │
│                                          │
│    *** READY TO PLAY! ***               │
│  Use ARROW KEYS to move penguin!        │
│                                          │
│          [Your Penguin]                 │
│               🐧                         │
│                                          │
│     [Table]         [Table]             │
│        O               O                 │
│                                          │
└─────────────────────────────────────────┘

Wait 5 seconds...

! 👤  ← Customer appears here!
(left side)
```

## ✅ Checklist: Is Game Working?

- [ ] Waited 30-60 seconds for initialization
- [ ] See "*** READY TO PLAY! ***" message
- [ ] See penguin in center of screen
- [ ] See 4 tables (circles with legs)
- [ ] Arrow keys move the penguin
- [ ] Waited additional 5-10 seconds for first customer
- [ ] See small penguin with ! at left side
- [ ] Can press S near customer to seat them

If all checkboxes are checked, **YOUR GAME IS WORKING PERFECTLY!** 🎉

## 🎮 Controls Reminder

| Key | Action |
|-----|--------|
| **↑ ↓ ← →** | Move penguin |
| **S** | Seat customer (near ! penguin) |
| **O** | Take order (near seated customer) |
| **F** | Serve food (near customer who ordered) |
| **C** | Collect money (near customer with $) |
| **Q** | Quit game |

Enjoy your Penguin Diner! 🐧🍽️
