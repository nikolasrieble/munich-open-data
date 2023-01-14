<script>
	// @ts-nocheck

	import { onMount } from 'svelte';
	import { Map } from '@onsvisual/svelte-maps';
	import maplibre from 'maplibre-gl';
	let map;
	let zoom;
	let center = {};
	onMount(() => {
		map.addControl(new maplibre.NavigationControl(), 'top-left');
	});
</script>

<svelte:head>
	<title>About</title>
	<meta name="description" content="About this app" />
</svelte:head>

<div class="text-column">
	<h1>This should show a map below</h1>

	<span>
		<Map
			id="map"
			style="https://api.maptiler.com/maps/streets/style.json?key=wxZrbxq3dPx17ds8LO59"
			location={{ lng: 11.57500, lat: 48.13750, zoom: 12 }}
			bind:map
			bind:zoom
			bind:center
		/>
	</span>
</div>

<style>
	span {
		width: 100%;
		height: 100vh;
		position: relative;
	}
</style>
