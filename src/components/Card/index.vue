<template>
	<div class="card-container">
		<p class="card-main-text card-font-weight">{{pokemon.name}}</p>
		<p class="card-date-text card-font-weight">18-06-2019</p>
	</div>
</template>

<script>
export default {
	name: 'Card',
	props: {
		pokemon: Object,
	},
}
</script>

<style>
	.card-container {
		width: 70.5%;
		min-height: 50px;
		margin-top: 1%; 
		background-color: #f0f7fc;
		border-radius: 10px;
	}

	.card-main-text {
		font-size: 18px;
		color: #7e7e7e;
		text-transform: capitalize;
	}

	.card-font-weight {
		padding: 2px 15px;
	}

	.card-date-text {
		font-size: 15px;
		color: #a0a0a0;
	}
</style>


