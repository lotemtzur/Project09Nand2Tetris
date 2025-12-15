# New Features Implementation

## Summary of Changes

### 1. Queue System ✅
- Customers spawn in a visible queue at entrance
- Each customer has a queue position (0, 1, 2...)
- Spacing between customers: 20 pixels
- Queue position calculated: startX + (position * spacing)

### 2. Food Variety ✅
- 3 food types implemented:
  - Type 0: Burger (three layers)
  - Type 1: Pizza (triangle slice with pepperoni)
  - Type 2: Fish (fish shape with tail and eye)
- Each customer randomly assigned a food type when they order

### 3. Kitchen/Food Preparation System ✅
- Kitchen counter at bottom of screen (y=230)
- 3 food slots for simultaneous preparation
- Food prep time: ~12 seconds (configurable)
- Visual progress indicator while food cooks

## New Workflow

### Old Workflow:
1. Seat customer → 2. Take order → 3. Serve food → 4. Collect payment

### New Workflow:
1. Seat customer from queue
2. Take order (customer assigned random food type)
3. Order sent to kitchen (starts cooking)
4. Wait for food to be ready
5. Pick up food from kitchen
6. Serve food to customer
7. Collect payment

## Classes Created/Modified

### New Classes:
- `Kitchen.jack` - Manages kitchen counter and food preparation
- `FoodItem.jack` - Individual food items being prepared

### Modified Classes:
- `GameConfig.jack` - Added queue and kitchen settings
- `Customer.jack` - Added foodType and queuePosition fields
- `Penguin.jack` - Added carriedFoodType field
- `PenguinDinerGame.jack` - Needs major updates (IN PROGRESS)

## Remaining Work

The game logic in `PenguinDinerGame.jack` needs to be updated to:

1. **Spawn customers in queue positions**
   - Calculate X position based on queue index
   - Update queue when customers are seated

2. **Implement pseudo-random food selection**
   - Use a pre-defined array of "random" numbers
   - Cycle through for variety

3. **Add kitchen to game**
   - Create Kitchen instance
   - Draw kitchen counter at bottom
   - Update kitchen each frame

4. **Update handleTakeOrder()**
   - Assign random food type to customer
   - Send order to kitchen (kitchen.addOrder())
   - Don't give food to penguin immediately

5. **Add handlePickupFood()**
   - New action (key 'P') to pickup from kitchen
   - Check if food is ready
   - Pick up ANY ready food (not customer-specific)

6. **Update handleServe()**
   - Serve food to ANY customer waiting for food
   - Don't check if penguin.pickup) {
            return;
        }
        
        let i = 0;
        while (i < maxCustomers) {
            let customer = customers[i];
            if (~(customer = null)) {
                if (customer.getState() = 1) {
                    if (isNear(customer.getX(), customer.getY())) {
                        // Pseudo-random food type selection
                        let foodTypeIndex = (totalCustomersServed + i) - ((totalCustomersServed + i) / 3 * 3);
                        if (foodTypeIndex < 0) { let foodTypeIndex = 0; }
                        if (foodTypeIndex > 2) { let foodTypeIndex = 2; }
                        
                        do customer.setFoodType(foodTypeIndex);
                        do customer.takeOrder();
                        do kitchen.addOrder(foodTypeIndex);
                        let i = maxCustomers; // exit
                    }
                }
            }
            let i = i + 1;
        }
        return;
    }

## Current Status

**Files completed:**
- ✅ GameConfig.jack
- ✅ Kitchen.jack  
- ✅ FoodItem.jack
- ✅ Customer.jack (updated)
- ✅ Penguin.jack (updated)

**Files needing work:**
- ⏳ PenguinDinerGame.jack (major refactoring needed)

**Ready to compile:** NO - Need to finish PenguinDinerGame.jack first

## Testing Plan

Once complete, test:
1. Customers appear in visible queue
2. Queue updates when customer is seated
3. Food assigned randomly when taking order
4. Kitchen shows food being prepared
5. Can pick up any ready food
6. Can serve food to any waiting customer
7. Multiple food orders work simultaneously
