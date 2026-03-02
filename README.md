<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Retro Fast Car – Assembly Game</title>
</head>
<body>

    <h1>Retro Fast Car – Assembly Game</h1>

    <p>
        This project was developed as part of my <strong>Systems 1</strong> course in the first year of Computer Science. 
        The goal of the course was to understand computer architecture, low-level programming, interrupts, 
        memory-mapped I/O, and how hardware interacts with software.
    </p>

    <p>
        For this project, I built a small retro-style car game entirely in assembly language.
    </p>

    <h2>What This Project Demonstrates</h2>
    <ul>
        <li>Low-level programming in assembly</li>
        <li>Interrupt handling (keyboard + VSync)</li>
        <li>Memory-mapped I/O</li>
        <li>VRAM manipulation</li>
        <li>Sprite-based graphics</li>
        <li>Collision detection</li>
        <li>Basic game loop architecture</li>
        <li>Frame-based difficulty scaling</li>
    </ul>

    <h2>How the Retro Car Game Works</h2>
    <p>The player controls a car using the keyboard:</p>
    <ul>
        <li><strong>4</strong> → Move left</li>
        <li><strong>6</strong> → Move right</li>
    </ul>

    <p>The objective is to avoid obstacles and stay on the road. The game ends if:</p>
    <ul>
        <li>The car collides with an obstacle</li>
        <li>The car moves off the road (pavement collision)</li>
    </ul>

    <p>
        As the game progresses, the obstacle speed increases, making it more challenging over time.
    </p>

    <h2>Technical Highlights</h2>

    <h3>Interrupt Service Routine (ISR)</h3>
    <p>
        The game uses hardware interrupts to detect keyboard input and screen refresh events (VSync). 
        This allows the game to respond instantly to key presses and update the screen smoothly, 
        creating stable animation and responsive controls.
    </p>

    <h3>Custom Graphics (VRAM Tiles)</h3>
    <p>
        Instead of using built-in characters, I created custom 64×64 pixel graphics and loaded them 
        directly into video memory (VRAM). These custom tiles are used to build the car, obstacles, 
        and road elements.
    </p>

    <h3>Sprite System</h3>
    <p>The car is built from three separate sprites:</p>
    <ul>
        <li>Outline</li>
        <li>Lights</li>
        <li>Body</li>
    </ul>
    <p>
        Each obstacle is also a separate sprite with its own position and movement behavior.
    </p>

    <h3>Collision Detection</h3>
    <p>
        The game constantly checks the distance between the car and obstacles. If they get too close, 
        the game detects a collision and triggers a game-over screen.
    </p>

    <h3>Increasing Difficulty Over Time</h3>
    <p>
        The game tracks how many frames have passed. After a certain amount of time, the obstacles move faster. 
        This gradually makes the game more challenging, up to a maximum speed.
    </p>

    <h2>What I Learned</h2>
    <p>
        This project allowed me to apply core Systems 1 concepts in a practical and meaningful way. 
        I worked with stack initialization and register preservation inside interrupt service routines, 
        managed interrupt control using CLI/STI, and used bitwise operations such as SHR, SHL, AND, and OR 
        to manipulate packed position values.
    </p>

    <p>
        I also communicated directly with hardware through memory-mapped I/O and IN/OUT instructions, 
        while manually managing memory and VRAM without any abstractions.
    </p>

    <p>
        Through building this game entirely in assembly, I gained a deep understanding of how graphics are 
        constructed from raw memory, how hardware interrupts function internally, how a game loop operates 
        at the lowest level, and how timing and synchronization affect smooth animation.
    </p>

</body>
</html>
