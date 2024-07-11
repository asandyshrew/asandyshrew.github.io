<script>
import BingoCard from "$lib/BingoCard.svelte";


let prompts = [
    {name: "Prog"},
    {name: "Writing"},
    {name: "Writing"},
    {name: "Writing"},
    {name: "Writing"},
    {name: "Writing"},
    {name: "Writing"},
    {name: "Writing"},
    {name: "Writing"},
    {name: "Writing"},
    {name: "Writing"},
    {name: "Writing"},
    {name: "Writing"},
    {name: "Writing"},
    {name: "Writing"},
    {name: "Writing"}
]


</script>


<div class="container">
    <div class="board">
        {#each prompts as {name}}
            <BingoCard name={name} />
        {/each}
    </div>
</div>


<style>
    * {
        margin: 0;
        padding: 0;
    }

    .container {
        display: flex;
        justify-content: center;
        align-self: center;
    }

    .board {
        display: grid;
        height: min(calc(80vh - 5px), calc(80vw - 5px));
        aspect-ratio: 1 / 1;
        grid-template-columns: 1fr 1fr 1fr 1fr;
    }

</style>