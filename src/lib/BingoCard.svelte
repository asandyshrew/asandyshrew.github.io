<script>
    import {createEventDispatcher} from "svelte";

    export let name;
    export let id;

    const dispatch = createEventDispatcher();

    let activated = false; // was the function activated


    // TODO: GET ON CLICK TO WORK

    function onClick() {
        activated = !activated;

        // let element = document.getElementsByClassName("card");
        let element = document.getElementById("container" + String(id));
        // element.classList
        if (element != null) {
            if (activated) {
                element.classList.add("active");
            } else{
                element.classList.remove("active");
            }

            dispatch('message', {
                text: "activated",
                id: id
            });
        }
    }

    function onRelease(){

    }
</script>


<div class="card" class:active={activated} id={"container"+id}>
    <button on:click={onClick} type="button" class="btn btn-primary">
        <div class="card-body">
            <p>{name}</p>
        </div>
    </button>
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

    .active {
        background-color: green;
    }

    .card:hover {
        background-color: yellow;
    }

    button {
        display: block;
        width: 100%;
        height: 100%;
    }

    p {
        justify-content: center;
        align-content: center;
        word-wrap: break-word;
    }
</style>