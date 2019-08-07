<style scoped>
	a {
		text-decoration: none;
		color: white;
		cursor: pointer;
	}
</style>

<template>
	<div @mouseover="active = true" @mouseleave="active = false">
		<!--  link that will be actually displaying always -->
		<a :href="'/' + navigation">
			<slot></slot>
		</a>

		<!-- portal declaration to destination of html within it -->
		<portal :to="navigation">
			<div
				class="mega-menu"
				v-show="active"
				@mouseover="active = true"
				@mouseleave="active = false"
			>
				<div class="container">{{ navigation }}</div>
			</div>
		</portal>
	</div>
</template>

<script>
	export default {
		props: {
			navigation: { type: String, required: true }
		},
		data() {
			return {
				active: false
			};
		}
	};
</script>

