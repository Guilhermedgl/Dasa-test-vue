<template>
	<main>
	<Navbar />
		<section class="home-container">
				<input type="text" v-model="search" class="home-input" placeholder="Procure por um pokemon">
				<Card v-for="(pokemon, idx) in renderList()" v-bind:key="idx" v-bind:pokemon="pokemon" />
		</section>
	</main>
</template>

<script>
import Navbar from '../Navbar';
import Card from '../Card';

export default {
	name: 'Home',
	components: {
		Navbar,
		Card
	},
	props: {
		pokemonsList: Array,
	},
	data() {
		return {
			search: '',
		}
	},
	methods: {
			renderList(search) {
			const list = [...this.pokemonsList];
			return list.filter(pokemon => pokemon.name.includes(this.search));
		},
	},
}
</script>

<style>
	.home-container {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		margin-top: 3%;
	}

	.home-input {
		width: 70%;
		height: 30px;
		font-size: 15px;
		padding-left: 1%;
	}
</style>


