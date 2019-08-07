
<style>
	a {
		text-decoration: none;
		color: white;
	}
	.nav-container {
		background-image: linear-gradient(
			141deg,
			#9fb8ad 0%,
			#1fc8db 51%,
			#2cb5e8 75%
		);
	}
	.container {
		width: 80%;
		margin-left: auto;
		margin-right: auto;
	}
	.nav {
		color: white;
		font-size: 25px;
		font-family: Arial, Helvetica, sans-serif;
		display: flex;
		justify-content: space-between;
	}

	.nav-item {
		padding-top: 20px;
		padding-bottom: 20px;
	}

	.mega-menu {
		height: 300px;
		background: #ddd;
	}
</style>

<template>
	<div id="app">
		<div class="nav-container">
			<!-- the navigation is composed by a list of components that fetch their own data and use portal to display it elswhere on the page -->
			<nav class="nav container">
				<series-dropdown class="nav-item" navigation="catalog"
					>Catalog</series-dropdown
				>
				<series-dropdown class="nav-item" navigation="series"
					>Series</series-dropdown
				>
				<series-dropdown class="nav-item" navigation="podcast"
					>Podcast</series-dropdown
				>
				<series-dropdown class="nav-item" navigation="discussions"
					>Discussions</series-dropdown
				>
			</nav>
		</div>

		<!-- destination for portal comming from within the series-dropdown component -->
		<portal-target name="catalog"> </portal-target>
		<portal-target name="series"> </portal-target>
		<portal-target name="podcast"> </portal-target>
		<portal-target name="discussions"> </portal-target>
	</div>
</template>

<script>
	import SeriesDropdown from "./components/SeriesDropdown";

	export default {
		name: "app",

		components: {
			"series-dropdown": SeriesDropdown
		}
	};
</script>
