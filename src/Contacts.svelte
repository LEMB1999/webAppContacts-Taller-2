<script>

let contacts = [];
import {onMount} from 'svelte'
onMount(async ()=>{

    const response = await fetch("http://localhost:3000/localhost",{
        headers:{
            "Content-Type":"application/json",
            "Accept":"application/json"
        }
    })

    const data = await response.json();
    console.log("data:",data);
    contacts = data.contacts;

})

</script>


<div class="container-contacts">
	<h1>Contacts</h1>
	{#each contacts as contact}

	    <div>
			<p>{contact.name}</p>
			<p>{contact.email}</p>
			<p>{contact.phone}</p>
		</div>

	{/each}

</div>


<style>
	.container-contacts{
		display: grid;
		grid-template-columns: repeat(3,1fr);
	}
</style>