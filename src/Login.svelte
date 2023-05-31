<script>

    import {createEventDispatcher} from 'svelte'

    let email = "";
    let password = "";


        const dispatch = createEventDispatcher()


    async function handleClick(){

        const response = await fetch("http://localhost:3000/login",{
            method:"POST",
            headers:{
                "Content-Type":"application/json",
                "accept":"application/json"
            },
            body:JSON.stringify({email,password})
        })

        const data = await response.json();

        console.log("data:",data);

        dispatch('authenticated',{status:true})

    }

</script>


<div class="container-form">
    <h1>Login</h1>
    <input type="email" placeholder="Email"  bind:value={email} />
    <input type="password" placeholder="Password" bind:value={password} />  
    <button on:click={handleClick}>Login</button>
</div>


<style>
    .container-form{
        display: flex;
        flex-direction:column;
    }
</style>