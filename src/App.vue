<template>
  <div id="app">

      <JokeButton/>

      <NormalJoke/>

      <LoudJoke/>

      <SnakeJoke/>

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
}
</script>

<style>
html{
  background-color: lavender;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
