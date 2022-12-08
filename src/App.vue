<template>
  <div id="app">
      <!-- JokeButton at top -->
      <JokeButton/>

      <NormalJoke/>
      <!-- <div v-if="joke">
        <h1>{{joke}}</h1>
        <button @click="clearJoke">Clear</button>
      </div> -->

      <LoudJoke/>

      <SnakeJoke/>
      <!-- <button @click="clearJoke">Clear</button> -->
  </div>
</template>

<script>
import JokeButton from '@/components/JokeButton.vue';
import LoudJoke from '@/components/LoudJoke.vue';
import SnakeJoke from '@/components/SnakeJoke.vue';
import NormalJoke from '@/components/NormalJoke.vue';

export default {
  name: 'App',
  components: {
    JokeButton,
    LoudJoke,
    SnakeJoke,
    NormalJoke
  },
  data() {
    return {
      joke: null,
    }
  },
  methods: {
    // displayJoke(joke) {
    //   this.joke = joke;
    // },
    // clearJoke(){
    //   this.joke = null;
    // },
  },
  // mounted () {
  //   this.$root.$on(`displayJoke`, this.displayJoke);
  // },
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
</style>
