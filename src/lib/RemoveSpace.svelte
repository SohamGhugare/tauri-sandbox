<script>
    import { invoke } from "@tauri-apps/api/tauri";
    let raw = "";
    let res = "";

    async function removeSpace() {
        res = await invoke("remove_space", { raw });
    }
</script>

<div>
    <form class="row" on:submit|preventDefault={removeSpace}>
        <input
            id="remove-space-input"
            placeholder="Enter a string..."
            bind:value={raw}
        />
        <button type="submit">Submit</button>
    </form>
    <p>{res}</p>
</div>
