<script>

    // https://svelte.dev/examples/named-slots
    // export let img;
</script>

<div class="setting-widget">
    <div class="setting">
        <slot name="image" class="icon"></slot>
        <slot name="setting" class="setting-title">
<!--            <span class="missing">Missing Name</span>-->
        </slot>
    </div>
</div>

<style>



    .setting {
        display: inline-block;
        vertical-align: middle;
        white-space: nowrap;

        /*maybe change to em*/
        padding: 0 0 0 1.5vh;
        background: 0 0 no-repeat;
        background-size: 20px 20px;
        margin: 0 0 0.5em 0;
        line-height: 1.2;

        /* for the image */
        /*background-image: url(var(--background-image));*/
    }

    .icon {
        display: inline-block;
        height: 1em;
        border: solid 2px black;
    }

    image {
        display: inline-block;
        height: 1em;
        border: solid 2px black;
    }

    .setting-title {
        display: inline-block;

    }

</style>