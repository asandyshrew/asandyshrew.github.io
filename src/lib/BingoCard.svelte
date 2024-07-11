<script>
    export let name;


</script>


<div class="card">
    <div class="card-body">
        <p>{name}</p>
    </div>
</div>

<style>
    .card {
        /* bg to show i'm squared or not ? */
        background-image: linear-gradient( 45deg, transparent 50%, rgba(0, 0, 0, 0.5) 50%);
        aspect-ratio: 1/1;

        margin: 0 5px 5px 0;  /*instead playing around with grid gap gap */
        background-color: red;
    }

    p {
        word-wrap: break-word;
    }
</style>