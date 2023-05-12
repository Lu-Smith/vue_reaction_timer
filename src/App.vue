<template>
<h1>Ninja Reaction Timer</h1>
<button @click="start" :disabled="isPlaying">play</button>
<Block v-if="isPlaying" :delay="delay" @end="endGame" />
<Results :score="score" v-if="showResults" />
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
      score: null,
      showResults: false
    }

  },
  methods: {
    start() {
      this.delay = 1 + Math.random() * 4000
      this.isPlaying = true
      this.showResults = false
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
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

button[disabled] {
  opacity: 0.5;
  color: white;
  cursor: not-allowed;
}
</style>
