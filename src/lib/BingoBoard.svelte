<script>
import BingoCard from "$lib/BingoCard.svelte";

let width = 4;
let prompts = [
    {name: "Prog", id:0},
    {name: "Writing", id:1},
    {name: "Writing", id:2},
    {name: "Writing", id:3},
    {name: "Writing", id:4},
    {name: "Writing", id:5},
    {name: "Writing", id:6},
    {name: "Writing", id:7},
    {name: "Writing", id:8},
    {name: "Writing", id:9},
    {name: "Writing", id:10},
    {name: "Writing", id:11},
    {name: "Writing", id:12},
    {name: "Writing", id:13},
    {name: "Writing", id:14},
    {name: "Writing", id:15}
]
let won = false;

function handleMessage(event) {
    checkWin(event.detail.id);
}

function isTileActive(id) {
    if (id == null || id == undefined || id < 0) {
        return false;
    }

    return document.getElementById("container"+String(id)).classList.contains("active");
}

function checkVerticalLine(col) {
    for (let i = 0; i < width; i++) {
        if (!isTileActive((i*width) + col)) {
            console.log("index ", i);
            return false;
        }
    }
    return true;
}

function checkHorizontalLine(row) {
    for (let i = row * width; i < row * width + 4; i++) {
        if (!isTileActive(i)) {
            return false;
        }
    }
    return true;

}

function checkDiagonalLine(row, col) {
    let TL_BR_win = true;
    let BL_TR_win = true;

    // Check TL -> BR line
    for (let i = 0; i < width*width; i += width + 1) {
        if (!isTileActive(i)) {
            TL_BR_win = false;
        }
    }

    // Check BL -> TR Line
    for (let i = width-1; i < (width*(width-1) + 1); i += width - 1) {
        if (!isTileActive(i)) {
            BL_TR_win = false;
        }
    }

    return TL_BR_win || BL_TR_win;
}

// TODO: update to deal with no longer winning after unselecting a box
function checkWin(index) {
    let col = index % width;
    let row = Math.floor(index / width);
    console.log("> row: ", row);
    console.log("> col: ", col);


    // TODO: create winning line
    let win_vert = false;
    let win_horiz = false;
    let win_diag = false;
    win_vert = checkVerticalLine(col);
    win_horiz = checkHorizontalLine(row);
    win_diag = checkDiagonalLine(row, col);
    console.log(win_diag, "diagonal");

    if (win_horiz || win_vert || win_diag) {
        won = true;
        return true;
    }
    won = false;
    return false;
}


</script>


<div class="container">
    <div class="board">
        {#each prompts as {name, id}}
            <BingoCard name={name} id={id} on:message={handleMessage}/>
        {/each}
    </div>
</div>

<div>
    <p>
        {won}
    </p>
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