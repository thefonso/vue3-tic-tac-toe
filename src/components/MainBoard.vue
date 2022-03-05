<script>
import { ref } from 'vue'
export default {
  name: 'MainBoard',
  props: {
    msg: String
  },
  setup () {
    console.log('setup called')
    const squares = ref([])
    squares.value = Array(9).fill('')
    console.log('squares' + squares.value)
    return { squares }
  }
}
// Psuedo Code it
// What does a tic tac toe game need?
//
// - Blank board
// - Players
// - Piece names (X / Y )
// - Take turns
// - Check 4 Winnner
// - Check 4 Tie Game
// - Play Game
// - resetBoard
// - ------
// - AI - special feature
// - Look cool

</script>

<template>
  <h2>{{msg}}</h2>
  <div id="board">
    <div class="square" v-for="(square, index) in squares" :key="index">
      {{ square }}
    </div>
  </div>
</template>

<style scoped>
#board {
  border: 1px solid darkred;
  height: 315px;
  width: 310px;
  margin:0 auto;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
.square {
  background: #fff;
  border: 1px solid #999;
  /*float: left;*/
  font-size: 70px;
  font-weight: bold;
  line-height: 34px;
  height: 100px;
  width: 100px;
  margin-right: -1px;
  margin-top: -1px;
  padding: 0;
  text-align: center;
}
</style>
