# **Snake Game JS**

A simple yet engaging Snake Game built using JavaScript, HTML, and CSS. The game includes sound effects, a scoring system, and local high-score storage.

## **🎮 Features**

Classic Snake Gameplay – Move the snake to eat food and grow.

Keyboard Controls – Use arrow keys to navigate.

Sound Effects – Includes food, movement, and game over sounds.

Score Tracking – Displays current score and high score.

Collision Detection – Ends game on wall or self-collision.

Responsive Design – Works across different screen sizes.

## **🛠️ Technologies Used**

JavaScript – Game logic and interactivity

HTML & CSS – Game layout and styling

## **🚀 How to Play**

Start the Game – Press any arrow key.

Control the Snake – Use ArrowUp, ArrowDown, ArrowLeft, ArrowRight keys.

Eat the Food – Snake grows and score increases.

Avoid Collisions – Hitting walls or itself ends the game.

## **📜 Code Highlights**

Game Constants & Variables

Manages snake movement, food generation, and game state.

let inputDir = {x: 0, y: 0};
let speed = 19;
let score = 0;
let snakeArr = [{x: 13, y: 15}];
let food = {x: 6, y: 7};

Collision Detection

Checks if the snake collides with itself or the walls.

function isCollide(snake) {
    for (let i = 1; i < snake.length; i++) {
        if (snake[i].x === snake[0].x && snake[i].y === snake[0].y) return true;
    }
    if (snake[0].x >= 18 || snake[0].x <= 0 || snake[0].y >= 18 || snake[0].y <= 0) return true;
    return false;
}

Game Loop

Updates the snake and food positions at regular intervals.

function main(ctime) {
    window.requestAnimationFrame(main);
    if ((ctime - lastPaintTime) / 1000 < 1 / speed) return;
    lastPaintTime = ctime;
    gameEngine();
}

Keyboard Controls

Detects arrow key presses and moves the snake.

window.addEventListener('keydown', e => {
    moveSound.play();
    switch (e.key) {
        case "ArrowUp": inputDir = {x: 0, y: -1}; break;
        case "ArrowDown": inputDir = {x: 0, y: 1}; break;
        case "ArrowLeft": inputDir = {x: -1, y: 0}; break;
        case "ArrowRight": inputDir = {x: 1, y: 0}; break;
    }
});

## **📂 How to Run the Game**

1.Clone the repository:

git clone https://github.com/pranamya2425/snake-game-js.git

2.Open index.html in a browser.

3.Enjoy the game! 🎉

