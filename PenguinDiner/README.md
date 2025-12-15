# Penguin Diner Game - Nand2Tetris Project

A fun restaurant management game written in Jack language for the Nand2Tetris course!

## Game Description

You play as a penguin waitress running a diner in Antarctica. Customers (penguin guests) arrive and sit at tables. Your job is to:
1. Seat customers at available tables
2. Take their orders
3. Serve them food
4. Collect payment when they're done

The faster and more efficiently you serve customers, the better tips you'll receive!

## Files Included

- `Main.jack` - Entry point for the game
- `PenguinDinerGame.jack` - Main game logic and state management
- `Penguin.jack` - Player character (waitress penguin)
- `Customer.jack` - Customer penguin with states (waiting, seated, eating, etc.)
- `Table.jack` - Restaurant tables

## How to Play

### Controls:
- **Arrow Keys** - Move your penguin waitress around
- **S** - Seat a waiting customer at a table
- **O** - Take an Order from a seated customer
- **F** - Serve Food to a customer who ordered
- **C** - Collect payment from a finished customer
- **Q** - Quit game

### Gameplay Flow:
1. Wait for customers to arrive (they spawn automatically)
2. Move near a waiting customer and press **S** to seat them
3. Move near the seated customer and press **O** to take their order (you'll see a food icon)
4. Move near the customer again and press **F** to serve the food
5. Wait for the customer to finish eating
6. Move near them and press **C** to collect payment and earn points

### Scoring:
- Base tip per customer: 1-10 points (based on how fast you served them)
- Angry customers leave and you lose 5 points
- Keep customers happy by serving them quickly!

## How to Compile and Run

### Using the Nand2Tetris Jack Compiler:

1. Navigate to the PenguinDiner directory
2. Compile the Jack files:
   ```
   JackCompiler PenguinDiner
   ```
   Or compile each file individually with the Jack Compiler tool

3. Run in the VM Emulator:
   - Open the VM Emulator
   - Load Program: Select the PenguinDiner directory
   - Click "Run" to start the game

### Alternative - Using Course Software:

1. Open the Nand2Tetris VM Emulator
2. File → Load Program → Select the PenguinDiner folder
3. Set animation speed to "Fast" for better gameplay
4. Click "Run" button

## Game Features

- **4 Tables** - Manage multiple customers at once
- **Customer AI** - Customers have patience levels that decrease over time
- **Score System** - Earn points based on service speed
- **Visual Feedback** - Simple graphics show game state
- **Real-time Management** - Balance multiple customers simultaneously

## Technical Details

- Written in Jack programming language
- Uses Nand2Tetris OS libraries (Screen, Keyboard, Output, Memory, Sys)
- Object-oriented design with separate classes for game entities
- Implements game loop with state management
- Screen resolution: 512x256 pixels

## Tips for Success

1. Seat customers as soon as they arrive
2. Take orders promptly after seating
3. Serve food quickly to maximize tips
4. Keep track of multiple customers at different stages
5. Don't let customers wait too long or they'll leave angry!

## Known Limitations

- Simple graphics due to Hack platform constraints
- Maximum 4 customers at a time
- Basic collision detection
- Text-based UI elements

## Credits

Developed for the Nand2Tetris course (nand2tetris.org)
Inspired by the classic Penguin Diner Flash game

Enjoy serving your penguin customers! 🐧🍽️
