<script>
	import { createEventDispatcher } from "svelte";


	let count = 1;

	$: if (count < 0) count = 0;

	$: double = count * 2;
	$: trippled = count * 3;

    
    const dispatch = createEventDispatcher()

</script>

<div class="flex items-center gap-4">
	<button
		type="button"
		class="px-4 py-2 rounded bg-blue-600 text-white"
		on:click={() => {
			count--;
            dispatch('decrement')
		}}
	>
		-
	</button>
	<p>{count}</p>
	<button
		type="button"
		class="px-4 py-2 rounded bg-blue-600 text-white"
		on:click={() => {
			count++;
            dispatch('increment', count)
		}}
	>
		+
	</button>
</div>

<div class="mt-4">
	<p>{count}x2={double}</p>
	<p>{count}x3={trippled}</p>
</div>
