<script>
    import { createEventDispatcher } from 'svelte';
    let dispatch = createEventDispatcher();

    export let username = "";
    export let password = "";
    export let favColor;
    export let showErrorMessage;
    // password is going to be wahoowa21

    const logIn = () => {
        const user = {
            uName: username,
            pWord: password,
            fColor: favColor
        }
        dispatch("loggingIn", user);
    }

</script>

<div class ="background">
    <div class ="modal">
        <h1>Welcome, sign in below!</h1>
        <button on:click = {logIn}> Log in</button>
        <div class = "userpass">
            <label for="username">Username</label>
            <input type="text" id="username" bind:value={username}>

            <label for="password">Enter Password Given</label>
            <input type="text" id="password" bind:value={password}>

            <label for="favColor">Favorite Color (no spaces)</label>
            <input type="text" id="favColor" placeholder="lightblue" bind:value={favColor}>
        </div>
        <div class = "error">
            {#if showErrorMessage}
                <p>The password you entered was incorrect, or your username was blank.</p>
            {/if}
        </div>
    </div>
</div>

<style>

    .background{
        width: 100%;
        height: 100%;
        background-color: rgb(0, 0, 157);
        margin: 0 auto;
        position: fixed;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
    }

    .modal{
        width: 50%;
        height: 70%;
        background-color: white;
        margin: auto;
        border-radius: 30px;
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
    }

    button{
        color: white;
        background-color: rgb(0, 0, 157);
        font-weight: bold;
        font-size: 16px;
        padding: 15px;
        border-radius: 10px;
        position: absolute;
        left: 50%;
        top: 85%;
        transform: translate(-50%, -50%);
    }

    h1{
        color: rgb(0, 0, 157);
        padding: 10px;
        text-align: center;
    }

    .userpass{
        position: absolute;
        left: 50%;
        top: 45%;
        transform: translate(-45%, -50%);
        color: rgb(0, 0, 157);
        font-weight: bold;
        font-size: 16px;
    }

    input{
        margin-bottom: 20px;
    }

    .error{
        color: red;
        width: 70%;
        position: absolute;
        left: 68%;
        top: 73%;
        transform: translate(-73%, -68%);
        margin: 5px;
    }


</style>