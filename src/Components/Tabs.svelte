<script>
    /* passing data from parent to child therefore must use props */
    /* Given that they are prop elements when declaring Tabs in App.svelte must pass them in */
    export let tabs;
    export let activeTab;
    export let favColor;

    /* ul tags are used when generating lists and <li> are the list components*/
    /* When a link is clicked on we want to send a custom dispatch to the app component (sending data child to parent)*/
    /* On a click event we need to generate a custom dispatch. Given that the dispatch is passing info
    we need to put it in a wrapper function so it only executes when clicked*/
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();
</script>

<div class="tabs">
    <ul>
        {#each tabs as tab}
        <li style="background: {favColor}" on:click={ () => dispatch('changeTab', tab)}>
            <div class:active={activeTab === tab}> {tab} </div>
        </li>
        {/each}
    </ul>
</div>


<style>
    /*  tabs is the group of tabs we want to change the margin, padding, and border in that field
    ul is the list, so we can use flexbox and other to change how the list is displayed (we want the
    list to be horizotal so use flexbox). li can be used to modify the tabs and class active modifies the 
    active tab*/

    ul{
        display: flex;
        justify-content: center;
        list-style: none;
    }

    li{
        border: 3px solid;
        border-color: rgb(0, 0, 176);
        font-weight: bold;
        cursor: pointer;
        margin: 30px 35px;
        margin-bottom: 45px;
          /* background: rgb(175, 175, 254);   */
        font-size: 22px;
        font-family: "Times New Roman", Times, serif;
        padding: 20px;
        border-radius: 15px;
    }

    li:hover{
        color: rgb(183, 0, 82);
    }

    .active{
        color:rgb(255, 63, 191);
    }


</style>