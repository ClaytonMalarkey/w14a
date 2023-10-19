<template>
    <button @click="fetchJoke">Get a Joke</button>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    methods: {
      async fetchJoke() {
        try {
          const response = await axios.get('https://ron-swanson-quotes.herokuapp.com/v2/quotes');
          const joke = response.data[0];
          this.$emit('jokeFetched', joke); // Emit the event with the fetched joke
        } catch (error) {
          console.error('Error fetching joke:', error);
        }
      }
    }
  }
  </script>
  