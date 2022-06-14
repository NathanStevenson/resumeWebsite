<script>
    export let transcriptImg;
    export let showTranscript;

    import { createEventDispatcher} from 'svelte';
    const dispatch = createEventDispatcher();

</script>


<div class="backdrop">
    {#if showTranscript}
        <div class="button">
            <button on:click={() => dispatch("closeTranscript")}>X</button>
        </div>
        <img src={transcriptImg} alt="Transcript">
    {/if}
</div>

<style>

    .backdrop{
        background: rgba(0, 0, 0, 0.2);
        text-align: center;
        width: 100%;
        height: 100%;
        margin-top: 30px;
        margin-bottom: 40px;
    }

    button{
        border-radius: 50%;
        font-size: 20px;
        cursor: pointer;
        margin: 10px;
    }

    button:hover{
        color: red;
    }

    .button{
        position: absolute; left: 370px;
    }

    img{
        padding: 10px;
    }


</style>