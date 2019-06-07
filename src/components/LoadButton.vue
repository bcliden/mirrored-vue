<template>
  <button @click="getText">
    Load Random
  </button>
</template>

<script>
import axios from 'axios';

export default {
  methods: {
    getText() {
      axios.get('https://api.punkapi.com/v2/beers/random')
        .then((response) => {
          const beer = response.data[0];
          this.$emit('newContent', `${beer.name}. ${beer.tagline} ${beer.description}`);
        })
        .catch(err => console.error(err));
    },
  },
};
</script>

<style scoped>
button {
  color: white;
  padding: 5px 10px;
  background-color: var(--vue-green);
  border: 1px solid var(--vue-dark-green);
  cursor: pointer;

  margin-left: 0.5rem;
}
</style>
