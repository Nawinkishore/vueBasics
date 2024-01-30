<template>
    <div class="text-center mt-8">
      <h1 class="text-3xl font-bold mb-4">Tic Tac Toe</h1>
      <div class="grid grid-cols-3 gap-2">
        <!-- Outer loop for rows -->
        <div v-for="(row, rowIndex) in board" :key="rowIndex" class="flex">
          <!-- Inner loop for cells in each row -->
          <div
            v-for="(cell, colIndex) in row"
            :key="colIndex"
            class="h-16 w-16 bg-green-400 border border-black flex items-center justify-center cursor-pointer text-2xl font-bold transition duration-300 ease-in-out"
            @click="cellClicked(rowIndex, colIndex)"
          >
            {{ cell }}
          </div>
        </div>
      </div>
      <div class="mt-4 text-xl font-bold" v-if="gameStatus !== 'In Progress'">
        {{ gameStatus }}
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        board: [
          [null, null, null],
          [null, null, null],
          [null, null, null]
        ],
        currentPlayer: 'X',
        gameStatus: 'In Progress'
      };
    },
    methods: {
      cellClicked(rowIndex, colIndex) {
        if (!this.board[rowIndex][colIndex] && this.gameStatus === 'In Progress') {
          this.$set(this.board[rowIndex], colIndex, this.currentPlayer);
          this.checkWinner();
          this.checkDraw();
          this.togglePlayer();
        }
      },
      checkWinner() {
        // Add logic to check for a winner
      },
      checkDraw() {
        // Add logic to check for a draw
      },
      togglePlayer() {
        this.currentPlayer = this.currentPlayer === 'X' ? 'O' : 'X';
      }
    }
  };
  </script>
  
  <style scoped>
  /* Add any additional styling here */
  </style>
  