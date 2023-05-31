<script>
	import Contacts from './Contacts.svelte';
	import Form from './Form.svelte'
	import Login from './Login.svelte'

	let isAuthenticated = false;

	function userAuthenticated(){
		 isAuthenticated = true;
	}

</script>

<div class="container-main">
	{#if !isAuthenticated}
	    <Login on:authenticated={ userAuthenticated }/>
	{:else}
	    <Contacts />
		<Form />
	{/if}
</div>

<style>
	.container-main{
		max-width: 400px;
	}
</style>