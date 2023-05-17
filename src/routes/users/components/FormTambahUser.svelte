<script>
	import { createEventDispatcher } from 'svelte';

	let nama = '';
	let email = '';
	let website = '';

	const dispatch = createEventDispatcher();
	const onSubmit = () => {
		dispatch('tambahData', {
			nama,
			email,
			website
		});
		nama = email = website = '';
	};
</script>

<form class="flex gap-3" on:submit|preventDefault={onSubmit}>
	<input bind:value={nama} type="text" placeholder="Masukkan Nama" />
	<input bind:value={email} type="email" placeholder="Masukkan Email" />
	<input bind:value={website} type="text" placeholder="Masukkan Website" />
	<button>Tambah Data</button>
</form>

<style>
	input {
		@apply border bg-gray-200 px-4 py-2;
	}
	button {
		@apply bg-green-500 text-white px-4 py-2 rounded;
	}
</style>
