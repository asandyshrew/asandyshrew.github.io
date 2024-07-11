<script>
import BingoCard from "$lib/BingoCard.svelte";

// let outer = document.getElementById('outer'),
//     wrapper = document.getElementById('wrap'),
//     maxWidth  = outer.clientWidth,
//     maxHeight = outer.clientHeight;
//
// window.addEventListener("resize", resize);
// resize();

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
    {name: "Writing"}
]

// function resize() {
//     let scale;
//     let width = window.innerWidth;
//     let height = window.innerHeight;
//
//     let isMax = width >= maxWidth && height >= maxHeight;
//
//     scale = Math.min(width/maxWidth, height/maxHeight);
//     outer.style.transform = isMax?'':'scale(' + scale + ')';
//     wrapper.style.width = isMax?'':maxWidth * scale;
//     wrapper.style.height = isMax?'':maxHeight * scale;
// }

</script>



<div class="board">
    {#each prompts as {name}}
        <BingoCard name={name} />
    {/each}

</div>


<style>
    * {
        margin: 0;
        padding: 0;
    }

    .board {
        /* TODO: Make it so entire board fits on screen */
        display: grid;
        height: min(calc(50vh - 5px), calc(50vw - 5px));
        aspect-ratio: 1 / 1;
        grid-template-columns: 1fr 1fr 1fr 1fr;
    }

    .board {
        counter-reset: test;
    }

</style>