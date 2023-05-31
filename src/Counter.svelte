<script>
	export let initialCounter = 0;
	let contador = initialCounter;

	function handleClick(){
		 contador++;
	}

</script>

<main>
	<p>{contador}</p>
	<button on:click={handleClick}>increment</button>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>