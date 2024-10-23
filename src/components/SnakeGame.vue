<template>
    <div class="snake-game">
      <canvas ref="gameCanvas" :width="canvasWidth" :height="canvasHeight"></canvas>
      <div class="scoreboard">
        <p>Score: {{ score }}</p>
        <p>Best Score: {{ bestScore }}</p>
      </div>
      <div v-if="!isGameRunning" class="start-message">
        <p>Press Space to Start</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        canvasWidth: 400,
        canvasHeight: 400,
        snake: [
          { x: 10, y: 10 },
          { x: 9, y: 10 },
          { x: 8, y: 10 }
        ],
        direction: { x: 1, y: 0 },
        food: { x: 15, y: 15 },
        gridSize: 20,
        gameInterval: null,
        isGameRunning: false,
        score: 0,
        bestScore: 0,
        initialSnakeLength: 7
      };
    },
    mounted() {
      window.addEventListener("keydown", this.handleKeydown);
      this.drawInitialGame();
    },
    beforeDestroy() {
      window.removeEventListener("keydown", this.handleKeydown);
      clearInterval(this.gameInterval);
    },
    methods: {
      drawInitialGame() {
        const ctx = this.$refs.gameCanvas.getContext("2d");
        this.drawGame(ctx);
      },
      startGame() {
        if (this.isGameRunning) return;
        this.resetGame();
        const ctx = this.$refs.gameCanvas.getContext("2d");
        this.gameInterval = setInterval(() => {
          this.updateGame(ctx);
        }, 100);
        this.isGameRunning = true;
      },
      resetGame() {
        this.snake = [
          { x: 10, y: 10 },
          { x: 9, y: 10 },
          { x: 8, y: 10 }
        ];
        this.direction = { x: 1, y: 0 };
        this.score = 0;
        this.placeFood();
        clearInterval(this.gameInterval);
      },
      updateGame(ctx) {
        this.moveSnake();
        if (this.checkCollision()) {
          alert("Game Over!");
          this.bestScore = Math.max(this.score, this.bestScore);
          this.isGameRunning = false;
          clearInterval(this.gameInterval);
          return;
        }
        if (this.eatFood()) {
          this.score++;
          this.placeFood();
        }
        this.drawGame(ctx);
      },
      drawGame(ctx) {
        ctx.clearRect(0, 0, this.canvasWidth, this.canvasHeight);
  
        ctx.fillStyle = "red";
        ctx.fillRect(this.food.x * this.gridSize, this.food.y * this.gridSize, this.gridSize, this.gridSize);
  
        ctx.fillStyle = "green";
        this.snake.forEach(segment => {
          ctx.fillRect(segment.x * this.gridSize, segment.y * this.gridSize, this.gridSize, this.gridSize);
        });
      },
      moveSnake() {
        const head = { x: this.snake[0].x + this.direction.x, y: this.snake[0].y + this.direction.y };
        this.snake.unshift(head);
        if (this.snake.length > this.initialSnakeLength) {
          this.snake.pop();
        }
      },
      checkCollision() {
        const head = this.snake[0];
        if (head.x < 0 || head.x >= this.canvasWidth / this.gridSize || head.y < 0 || head.y >= this.canvasHeight / this.gridSize) {
          return true;
        }
        for (let i = 1; i < this.snake.length; i++) {
          if (head.x === this.snake[i].x && head.y === this.snake[i].y) {
            return true;
          }
        }
        return false;
      },
      eatFood() {
        const head = this.snake[0];
        return head.x === this.food.x && head.y === this.food.y;
      },
      placeFood() {
        this.food.x = Math.floor(Math.random() * (this.canvasWidth / this.gridSize));
        this.food.y = Math.floor(Math.random() * (this.canvasHeight / this.gridSize));
      },
      handleKeydown(e) {
        if (e.code === "Space" && !this.isGameRunning) {
          this.startGame();
        }
  
        if (!this.isGameRunning) return;
  
        if (["ArrowUp", "ArrowDown", "ArrowLeft", "ArrowRight"].includes(e.code)) {
          e.preventDefault();
        }
  
        switch (e.code) {
          case "ArrowUp":
            if (this.direction.y === 0) this.direction = { x: 0, y: -1 };
            break;
          case "ArrowDown":
            if (this.direction.y === 0) this.direction = { x: 0, y: 1 };
            break;
          case "ArrowLeft":
            if (this.direction.x === 0) this.direction = { x: -1, y: 0 };
            break;
          case "ArrowRight":
            if (this.direction.x === 0) this.direction = { x: 1, y: 0 };
            break;
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .snake-game {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin-top: 20px;
  }
  
  canvas {
    background-color: #24283b;
    border: 2px solid #D499B9;
  }
  
  .scoreboard {
    margin-top: 10px;
    color: #ffffff;
    text-align: center;
  }
  
  .start-message {
    color: #ffffff;
    margin-top: 10px;
    font-size: 18px;
  }
  </style>