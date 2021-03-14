<template>
  <div id="app">
    <main class="flexbox">
      <Board id="board-1">
        <Card
          src="https://scontent.fmnl4-6.fna.fbcdn.net/v/t1.0-9/138678327_3946684432029394_1690651896473336140_o.jpg?_nc_cat=109&ccb=1-3&_nc_sid=09cbfe&_nc_eui2=AeEjqwMlwhGpwAn8Bs__H2xoFiTxCqq23eEWJPEKqrbd4aEUDrGAALZpr3TOlUXAgx66E2LCzq-KffVW3TwNj2ou&_nc_ohc=N_sWjSSJndgAX_bihkD&_nc_pt=1&_nc_ht=scontent.fmnl4-6.fna&oh=d6a10f663e6a3e22a70687dd9ccd42fa&oe=606F7F5F"
          id="card-1"
          draggable="true"
        >
          <p>Card 1</p>
        </Card>
      </Board>

      <Board id="board-2">
        <Card
          src="https://scontent.fmnl4-6.fna.fbcdn.net/v/t1.0-9/156668439_4084898351541334_3339129375738017872_o.jpg?_nc_cat=109&ccb=1-3&_nc_sid=e3f864&_nc_eui2=AeH015qZgrrumJAVxhlA9lV_IflI4kXQ7qkh-UjiRdDuqW8ZT6V50P65VRA__sPFJThYxDuLyrTI42KlRyiEDr1P&_nc_ohc=9WEISuXPxBcAX-K5xEM&_nc_pt=1&_nc_ht=scontent.fmnl4-6.fna&oh=bfbf38bb78d9b7b3a1c4a9a926d64c7e&oe=606F9D60"
          id="card-2"
          draggable="true"
        >
          <p>Card 2</p>
        </Card>
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
