<template>
  <div id="app">
    <JokeButton @jokeFetched="updateJoke" />
    <div>
      <button @click="displayNormal = true">Normal Joke</button>
      <button @click="displaySnake = true">Snake Joke</button>
      <button @click="displayLoud = true">Loud Joke</button>
    </div>
    <div v-if="displayNormal">{{ joke }}</div>
    <div v-if="displaySnake">{{ snakeJoke }}</div>
    <div v-if="displayLoud">{{ loudJoke }}</div>
  </div>
</template>

<script>
import JokeButton from './components/JokeButton.vue';

export default {
  data() {
    return {
      joke: '',
      snakeJoke: '',
      loudJoke: '',
      displayNormal: false,
      displaySnake: false,
      displayLoud: false
    };
  },
  methods: {
    updateJoke(newJoke) {
      this.joke = newJoke;
      this.snakeJoke = newJoke.replace(/ /g, '_');
      this.loudJoke = newJoke.toUpperCase();
      this.displayNormal = true;
      this.displaySnake = false;
      this.displayLoud = false;
    }
  },
  components: {
    JokeButton
  }
}
</script>
