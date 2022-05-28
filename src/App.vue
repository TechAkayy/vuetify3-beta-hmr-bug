<template>
	<v-app>
		<div
			style="width: 280px; min-width: 280px; max-width: 280px"
			v-for="(item, index) in items"
			:key="index"
			class="mb-3 ml-1"
		>
			<!-- Change color from "red" to "green", and save file, HMR doesn't apply, requires page refresh. Generally updates within v-for is not getting HMR applied correctly -->
			<v-btn class="ml-3" color="red" @click="addToCart(item)">v-btn</v-btn>

			<!-- Change color from "red" to "green", and save file, HMR applies correctly. Only difference from the above is the click handler doesn't have a parameter, no idea why it works here, but not above -->
			<v-btn class="ml-3" color="red" @click="addToCart()">v-btn</v-btn>
		</div>

		<!-- Change step from '5' to '10', and save file, HMR doesn't apply, requires page refresh. This is a HMR issue when updating an element that's not really within a v-for -->
		<v-slider
			v-model="slider3"
			thumb-color="purple"
			label="thumb-color"
			step="5"
			show-ticks="always"
			tick-size="4"
		></v-slider>
	</v-app>
</template>

<script>
	export default {
		data: () => ({
			items: [1, 2, 3]
		}),
		methods: {
			addToCart(item) {}
		}
	}
</script>
