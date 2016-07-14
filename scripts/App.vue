<template>
  <drawing-board v-if='this.player == 1'></drawing-board>
  <showing-board v-if='this.player == 2'></showing-board>
  <button v-if='this.player == 0' @click='draw'>我来画</button>
  <button v-if='this.player == 0' @click='guess'>我来猜</button>
  <button v-if='this.player == 2' @click='replay'>重新开始</button>
</template>

<script>
import Vue from 'vue'

import DrawingBoard from './components/drawing-board.vue'
import showingBoard from './components/showding-board.vue'

export default {
  data(){
    return {
      player: 0
    }
  },

  components: {
    DrawingBoard,
    showingBoard,
  },

  method: {
    draw() {
      this.player = 1
    },
    guess() {
      this.player = 2
    },
    replay() {
      this.player = 0
      location.reload()
    }
  }
}
</script>

<style>
  body {
    background: #fff;
  }
</style>
