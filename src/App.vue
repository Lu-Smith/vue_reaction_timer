<template>
<h1>Ninja Reaction Timer</h1>
<button @click="start" :disabled="isPlaying">play</button>
<Block v-if="isPlaying" :delay="delay" @end="endGame" />
<Results :score="score" />
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  components: {
    Block,
    Results
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null
    }

  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
button {
  padding: 10px 15px;
  font-size: 30px;
  font-weight: 600px;
  border-radius: 10px;
  box-shadow: 2px 2px 2px rgba(0, 0, 0, 0.5);
  background-color: red;
  transition: 200ms all ease-in-out;
  cursor: pointer;
}

button:hover {
  background-color: rgb(245, 62, 62);
  color: white;
  box-shadow: none;
}
</style>
