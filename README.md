# 🏎️ Retro Car Game (Assembly Language Project)

This project was developed as part of my Systems 1 course in the first year of Computer Science. The goal of the course was to understand computer architecture, low-level programming, interrupts, memory-mapped I/O, and how hardware interacts with software.

For this project, I built a small retro-style car game entirely in assembly language.

What This Project Demonstrates is 
  - low-level programming in assembly
  - Interrupt handling (keyboard + VSync)
  - Memory-mapped I/O
  - VRAM manipulation
  - Sprite-based graphics
  - Collision detection
  - Basic game loop architecture
  - Frame-based difficulty scaling


How does the Retro Car Game work?
The player controls a car that can move left and right using the keyboard:
  4 → Move left
  6 → Move right

The objective is to avoid obstacles and stay on the road. The game ends if:
  - The car collides with an obstacle
  - The car moves off the road (pavement collision)

As the game progresses, the obstacle speed increases, making it more challenging over time.


Technical Highlights
**Interrupt Service Routine (ISR)**
The game uses hardware interrupts to detect keyboard input and screen refresh events (VSync). This allows the game to respond instantly to key presses and update the screen smoothly, creating stable animation and responsive controls.

**Custom Graphics (VRAM Tiles)
**Instead of using built-in characters, I created custom 64×64 pixel graphics and loaded them directly into video memory (VRAM). These custom tiles are used to build the car, obstacles, and road elements.

**Sprite System**
The car is built from three separate sprites:
Outline
Lights
Body

Each obstacle is also a separate sprite with its own position and movement behavior.

**Collision Detection**
The game constantly checks the distance between the car and obstacles. If they get too close, the game detects a collision and triggers a game-over screen.

**Increasing Difficulty Over Time**
The game tracks how many frames have passed. After a certain amount of time, the obstacles move faster. This gradually makes the game more challenging, up to a maximum speed.

This project allowed me to apply core Systems 1 concepts in a practical and meaningful way. 
I worked with stack initialization and register preservation inside interrupt service routines, managed interrupt control using CLI/STI, and used bitwise operations such as SHR, SHL, AND, and OR to manipulate packed position values. 

I also communicated directly with hardware through memory-mapped I/O and IN/OUT instructions, while manually managing memory and VRAM without any abstractions.

Through building this game entirely in assembly, I gained a deep understanding of how graphics are constructed from raw memory, how hardware interrupts function internally, how a game loop operates at the lowest level, and how timing and synchronization affect smooth animation. 



