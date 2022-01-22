<template>
  <h1>nen jina</h1>
  <button @click="start" :disabled="isPlaying">play</button>
  <Block v-if="isPlaying" :delay="delay" @end="okayy"/>
  <Results v-show="shResult" :resu="score"/>
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
    return{
      isPlaying: false,
      delay: null,
      score: null,
      shResult: false,
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
    },
    okayy(eyy){
      this.score = eyy
      this.isPlaying = false
      this.shResult = true
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
  color: #2c3e50;
  margin-top: 60px;
}

button{
  width: 6rem;
  padding: 1.5em;
  cursor: pointer;
  background: aqua;
  border: 1px solid #2c3e50;
  border-radius: 5px;
}
</style>
