# 🐧 PENGUIN DINER - Complete Gameplay Guide

## 🎮 How the Game Works

### Game Overview
You control a penguin waitress in an Antarctic diner. Customers arrive automatically, and you must serve them quickly to earn tips!

## 👀 Visual Indicators - What You See

### Your Penguin (Player)
- **Larger penguin** with detailed body, white belly, eyes, beak, feet, and wings
- **When carrying order**: Shows a tray with food circle on the right side
- **You can MOVE**: Use arrow keys to move around the restaurant

### Customer States (Small penguins at tables)
Customers change appearance based on their state:

1. **🚶 WAITING (at entrance, left side)**
   - Shows **exclamation mark (!)** 
   - Standing at position (30, 120)
   - ACTION: Press **S** when near to seat them

2. **💭 SEATED (at table)**
   - Shows **thought bubble** (circle outline)
   - Ready to order
   - ACTION: Press **O** when near to take their order

3. **🍔 ORDERED (waiting for food)**
   - Shows **burger icon** floating above head
   - Waiting for you to bring food
   - ACTION: Press **F** when near (while carrying food) to serve

4. **🍴 EATING**
   - Shows **fork and food**
   - Customer is eating (automatic)
   - ACTION: Wait for them to finish

5. **💰 DONE (ready to pay)**
   - Shows **money symbol ($)**
   - Ready to leave and pay
   - ACTION: Press **C** when near to collect payment

### Tables
- **4 Round tables** with white surface and center leg
- Positions: Top-left (120,80), Top-right (320,80), Bottom-left (120,160), Bottom-right (320,160)

## 🎯 Step-by-Step Gameplay

### Complete Service Workflow:

```
1. CUSTOMER ARRIVES
   └─> New customer appears at entrance (left side) with ! mark
   
2. SEAT CUSTOMER (Press S)
   └─> Move near waiting customer
   └─> Press S to seat at empty table
   └─> Customer moves to table, shows thought bubble
   
3. TAKE ORDER (Press O)
   └─> Move near seated customer
   └─> Press O to take their order
   └─> Your penguin shows tray with food
   └─> Customer shows burger icon above head
   
4. SERVE FOOD (Press F)
   └─> Move near customer with burger icon
   └─> Press F to serve the food
   └─> Your penguin's tray disappears
   └─> Customer shows fork, starts eating (automatic)
   
5. CUSTOMER EATS (Wait)
   └─> Customer automatically eats for ~50 patience units
   └─> When done, money symbol appears
   
6. COLLECT PAYMENT (Press C)
   └─> Move near customer with $ symbol
   └─> Press C to collect payment
   └─> You earn 1-10 points (faster = better tip!)
   └─> Customer disappears, table is free
```

## 🕹️ Controls Reference

| Key | Action | When to Use |
|-----|--------|-------------|
| **↑ ↓ ← →** | Move Penguin | Always - navigate the restaurant |
| **S** | Seat Customer | Near waiting customer (! mark) |
| **O** | Take Order | Near seated customer (thought bubble) |
| **F** | Serve Food | Near customer who ordered (burger icon), ONLY when carrying food |
| **C** | Collect Payment | Near finished customer ($ symbol) |
| **Q** | Quit Game | Anytime |

## ⚠️ Important Gameplay Notes

### YOU CAN MOVE!
- **Use arrow keys constantly** to move between customers and tables
- You must be **near** a customer (within ~25 pixels) to interact
- Move to the entrance to greet new customers
- Move to tables to take orders and serve food

### Customer Spawning
- New customers appear **automatically every ~100 time units**
- They spawn at the **left side entrance** (x=30, y=120)
- Maximum 4 customers at once (one per table)
- Look for the **! exclamation mark** to spot new arrivals

### Order Management
- You can only carry **ONE order at a time**
- Take order (O) → Serve food (F) → Then you can take another order
- Don't try to take multiple orders - serve the first one first!

### Patience System
- Each customer has a **patience counter**
- Patience decreases over time (shown in code, not visually)
- **Faster service = Better tips** (1-10 points)
- If patience runs out, customer **leaves angry** and you **lose 5 points**

### Scoring
- Base tip per customer: **1-10 points**
- Points based on remaining patience when you collect payment
- Angry customers: **-5 points**
- Score displayed at top right

## 🎓 Pro Tips

1. **Watch the entrance** - New customers spawn there with ! mark
2. **Seat customers immediately** - Don't let them wait too long
3. **Take orders quickly** - Seated customers (thought bubble) should be served fast
4. **Move efficiently** - Plan your route between tables
5. **One order at a time** - Complete one service cycle before starting another
6. **Collect payment promptly** - Free up tables for new customers

## 🐛 Testing the Interactivity

To verify the game works:

1. **Start game** - See your penguin and 4 tables
2. **Wait ~10 seconds** - A customer should appear at left side with !
3. **Use arrow keys** - Move your penguin around (YOU CAN MOVE!)
4. **Move to customer** - Go to the customer with ! mark
5. **Press S** - Customer should move to a table
6. **Move to table** - Go to the seated customer
7. **Press O** - Your penguin should show a tray
8. **Press F** - Customer should start eating (fork appears)
9. **Wait** - Customer will finish and show $ symbol
10. **Press C** - Collect payment, score increases!

## 📊 Game State Display

Top of screen shows:
```
PENGUIN DINER                    Score: XXX
Controls: Arrows=Move, S=Seat, O=Order, F=Serve, C=Collect, Q=Quit
```

## 🎨 Visual Summary

```
Screen Layout:
┌─────────────────────────────────────────┐
│ PENGUIN DINER          Score: 0         │
│ Controls: ...                           │
├─────────────────────────────────────────┤
│                                          │
│     [Table 1]       [Table 2]           │
│         O               O                │
│      👤💭            👤🍔               │
│                                          │
│  ! 👤  [Your Penguin] 🐧                │
│   (New)                                  │
│                                          │
│     [Table 3]       [Table 4]           │
│         O               O                │
│      👤💰            👤🍴               │
│                                          │
└─────────────────────────────────────────┘

Legend:
O = Table
🐧 = Your penguin (you can MOVE with arrows!)
👤 = Customer
! = Waiting
💭 = Seated (ready to order)
🍔 = Ordered (needs food)
🍴 = Eating
💰 = Done (collect payment)
```

Enjoy your Penguin Diner adventure! 🐧🍽️✨
