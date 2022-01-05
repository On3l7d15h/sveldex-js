<script>
    // importaciones
    import Search from "./Search.svelte";
    import Data from "./Data.svelte"

    //variables
    let idpk;
</script>

<div class="container">
    <Search bind:idpkmn={idpk} />
    <Data {idpk}/>
</div>

<style>
    /* container styles! */

    .container
    {
        width: 100%;
        max-width: 80%;
        display: flex;
        flex-direction: column;
        flex-wrap: wrap;
        justify-content: center;
        align-items: center;
        background: var(--c-tomato-cake);
    }   

</style>