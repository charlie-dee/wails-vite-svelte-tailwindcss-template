<script>
	import logo from './assets/images/logo-dark.svg';

	let name = "";
	let greeting = "";

	function greet() {
		// @ts-ignore
		window.go.main.App.Greet(name).then((/** @type {string}  */ result) => {
			greeting = result;
		});
	}
</script>

<main>
	<div class="h-screen flex flex-col items-center justify-center bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 mx-auto overflow-auto">
		<img class="object-fill w-96 h-96 -mt-28" alt="Wails Dragon - Super Cool Stuff." src={logo}>
		
			<input aria-label="Enter your name" type="text" id="name" class="text-sm py-4 px-4 h-2 rounded mb-2" bind:value={name}>
			<button class="bg-blue-500 hover:bg-blue-900 text-white font-bold py-2 px-4 rounded" on:click={greet}>Greet</button>
		
		{#if greeting}
			<div class=" text-black font-bold text-xl">{greeting}</div>
		{/if}
	</div>
</main>

<style>
 
</style>
