<template>
  <h1 style="font-size:80px">Reaction Timer</h1>
  <button @click="start" :disabled="isplaying">Play!!!</button>
  <Block v-if="isplaying" :delay="delay" @end="endGame"/>
  <Results v-if="showresults" :score="score"/>
</template>

<script>
import Block from "@/components/Block.vue"
import Results from "@/components/Results.vue"

export default {
  name: "App",
  components: { Block, Results },


  data() {
    return {
      isplaying: false,
      delay: null,
      score: null,
      showresults:false
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isplaying = true;
      this.showresults=false;
    },
    endGame(reactionTime){
      this.score=reactionTime
      this.isplaying=false
      this.showresults= true
    }
  }
};
</script>

<style>
*{background-color: blanchedalmond;}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444444;
  margin-top: 60px;
  
}
button{
  background-color: darkmagenta;
  color: white;
  border-radius: 4px;
  font-size: 20px;

cursor: pointer;}

button[disabled]{
  opacity: 0.2;
  cursor:not-allowed;
}
</style>
