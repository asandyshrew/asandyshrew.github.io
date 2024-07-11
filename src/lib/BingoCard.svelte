<script>
    export let name;
    let activated = false; // was the function activated


    // TODO: GET ON CLICK TO WORK

    function onClick() {
        activated = !activated;

        // let element = document.getElementsByClassName("card");
        let element = document.getElementById("container");
        // element.classList
        if (element != null) {
            element.classList.toggle("active");
        }
    }
</script>


<div class="card" id="container" on:click={onClick}>
    <div class="card-body">
        <p>{name}</p>
    </div>
</div>

<style>
    .card {
        aspect-ratio: 1/1;

        margin: 0 5px 5px 0;  /*instead playing around with grid gap gap */
        background-color: red;

        display: flex;
        justify-content: center;
        align-items: center;
        border: 3px solid green;
    }

    .card .activated {
        background-color: green;
    }

    .card:hover {
        background-color: yellow;
    }

    p {
        justify-content: center;
        align-content: center;
        word-wrap: break-word;
    }
</style>