<template>
  <div id="app">
    <Home v-bind:pokemonsList="pokemonsList" />
  </div>
</template>

<script>
import Home from './components/Home';
import axios from 'axios';

export default {
  name: 'app',
  components: {
    Home
  },
  data() {
    return {
      pokemonsList: [],
    }
  },
  	mounted() {
		axios.get('https://pokeapi.co/api/v2/pokemon')
			.then(response => this.pokemonsList = response.data.results)
			.catch(error => console.log(error))
	},
}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
  }
</style>
