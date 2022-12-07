<template>
  <div id="app">
    <JokeButton/>
  </div>
</template>

<script>
import JokeButton from '@/components/JokeButton.vue';

export default {
  name: 'App',
  components: {
    JokeButton,
  },
  data() {
    return {
      jokes: []
    }
  },
  methods: {
    displayJoke(joke) {
      this.jokes.push(joke)
    }
  },
  mounted () {
    this.$root.$on(`displayJoke`, this.displayJoke);
  },
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
