<script>
	
    let email = "";
    let phone = "";
    let name = "";

    async function handleClick(){

       const response = await fetch("http://localhost:3000/contacts",{
            method:"POST",
            headers:{
                "Content-Type":"application/json",
                "Accept":"application/json",
                "API-KEY":""
            },
            body: JSON.stringify({name,phone,email})
       });

       const data = await response.json();

       console.log("data:",data);


    }

</script>

<div class="container-form">
    <h1>Create Contact</h1>
	<input type="text"  bind:value={name}  placeholder="Name"  />
    <input type="phone" bind:value={phone} placeholder="Phone" />
    <input type="email" bind:value={email} placeholder="Email" />
    <button on:click={ handleClick } >Create</button>
</div>

<style>
	.container-form {
		display: flex;
        flex-direction: column;
	}
</style>