<script>
	import { createEventDispatcher } from "svelte";

    export let show = false
    const dispatch = createEventDispatcher()
</script>

<button on:click={()=> {
    show=!show
    if(show) dispatch('opened')
    else dispatch('closed')
}}>
    Buka
</button>

{#if show}
<div>
        ini data
</div>
{/if}