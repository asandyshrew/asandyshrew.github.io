<script>
    import BingoBoard from "$lib/BingoBoard.svelte";
    import Setting from "$lib/Setting.svelte";
    import Banner, {Label} from "@smui/banner";
</script>
<Banner>
    <Label slot="label">This is a temporary banner</Label>
    <svelte:fragment slot="actions">
        <button>secondary button</button>
        <button>primary button</button>
    </svelte:fragment>
</Banner>/


<BingoBoard />

/* Save as image */
