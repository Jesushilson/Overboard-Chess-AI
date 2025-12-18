# Timeline


## Week 0 - Prepare:
**Goal: Gain core skills and get hardware so development starts smoothly.**

* Learn OpenCV fundamentals
  * Frame capture, preprocessing, contours, perspective transforms
* Learn Python multithreading / multiprocessing
  * Thread lifecycle, queues, message passing
* Strengthen Flask and Flutter communication knowledge
  * REST basics, WebSockets, JSON payload design
* Order items
  * Raspberry Pi, webcam, stand, SD card, power supply

## Week 1 - Board Recognition:
**Goal: Get the Pi to reliably identifying the chessboard and grid coordinates.**

* Install OpenCV on Raspberry Pi and verify camera feed
* Implement board detection
  * Detect edges/corners
  * Apply perspective correction
* Create grid-mapping system
  * 8×8 coordinate mapping
  * Identify each square region consistently with correct coordinate 

## Week 2 - Piece and Move Recognition:
**Goal: The system recognizes piece types and detects changes between frames.**

* Train or build piece recognition model
  * Classical CV or ML classifier
  * Detect pieces from top-down view reliably
* Compute move
  * Compare frame N vs. frame N+1
  * Identify the source square and the desiniation square
  * Be able to handle captures and weird moves

## Week 3 - Event Bus and State Manger:

**Goal: Add real architecture**

* Implement Event Bus
  * Channels/queues for each thread
  * Events: board_update, move_detected, error, obstruction, AI_move, etc.
* Implement State Manager
  * Stores board state, legal moves, game history
  * Integrates with python-chess
* Ensure all threads communicate without blocking

## Week 4 - Implement the AI Engine and add Continutiy:
**Goal: Add Stockfish, review mode, and smooth continuity across moves.**

* Integrate Stockfish engine
  * Feed game state into Stockfish
  * Receive AI moves
* Implement AI move announcement
* Add move review mode
  * Evaluate moves using Stockfish scores
* Add continuity handling
  * Detect board drift
  * Re-stabilize grid
  * Recover state after obstruction

## Week 5 - Mobile App 
**Goal: Create Flutter mobile app and ensure smooth, robust UI.**

* Flutter UI Implementation
  * Build UI screens for:
    * Live game tracking
    * Move confirmations
    * AI move announcement
* Basic Error Handling
  * Phone should display:
    * “Obstruction detected”
    * “Move unclear—please confirm”
    * “Recenter the board”
   
## Week 6 - Pi and App Connection + Optimization and Testing
**Goal: Conenct Pi to Flutter app. Optimize the system to ensure smooth, robust communication.**

* Mobile Connectivity
  * Implement Flask endpoints for:
    * Sending detected moves to the phone
    * Receiving user confirmations
    * Sending AI moves to the phone
    * Starting/stopping a game
  * Add WebSocket support (MAYBE) for real-time updates
  * Implement a clean JSON schema for all messages (moves, errors, states)
* Test Routines
  * Create testing scripts for:
    * Simulated frame sequences
    * Artificial obstructions
    * Fake move events
  * Ensure the flow from Pi to Phone to Pi works.
* Performance Optimization
  * Reduce latency in:
    * Frame capture
    * Vision processing
    * Event pipeline
    * Profile sample hotspots
## Week 7 - Not Yet
