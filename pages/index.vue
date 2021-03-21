<template>
  <div id="app">
    <main class="flexbox scroll">
      <Board id="board-1">
        <Card
          v-for="(index, value) in new Array(15)"
          :key="value.key"
          :id="`card-${value}`"
          :piece-value="value"
          draggable="true"
        />
      </Board>
    </main>
  </div>
</template>

<script>
import Board from "../components/Board.vue";
import Card from "../components/Card.vue";

export default {
  components: {
    Board,
    Card,
  },
};
</script>

<style>
Board* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: #f3f3f3;
}

.flexbox {
  display: flex;
  justify-content: space-between;
  width: 100%;
  max-width: 768px;
  height: 100vh;
  overflow: hidden;
  margin: 0 auto;
  padding: 15px;
}

.flexbox .board {
  display: flex;
  flex-direction: column;
  width: 100%;
  max-width: 300px;
  background-color: #313131;
  padding: 15px;
}

.flexbox .board .card {
  padding: 15px 25px;
  background-color: #f3f3f3;
  cursor: pointer;
  margin-bottom: 15px;
}
</style>
