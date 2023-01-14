<script>
	// @ts-nocheck

	import { onMount } from 'svelte';
	import { Map } from '@onsvisual/svelte-maps';
	import { longitude, latitude } from './munich';
	import maplibre from 'maplibre-gl';
	let map;
	let zoom = 12;
	let center = {};
	onMount(() => {
		map.addControl(new maplibre.NavigationControl(), 'top-left');
	});
</script>

<svelte:head>
	<title>About</title>
	<meta name="Map" content="Map" />
</svelte:head>

<div class="text-column">
	<h1>Welcome to Munich</h1>

	<span>
		<Map
			id="map"
			style="https://api.maptiler.com/maps/streets/style.json?key=wxZrbxq3dPx17ds8LO59"
			location={{ lng: longitude, lat: latitude, zoom }}
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
