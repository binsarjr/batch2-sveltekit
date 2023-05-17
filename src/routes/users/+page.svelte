<script>
    // @ts-nocheck
	import FormTambahUser from "./components/FormTambahUser.svelte";

    let items = [
        {
            name: "binsar",
            email: "binsarjr121@gmail.com",
            website: 'binsar.dev',
        }
    ]


    const tambahData = (item) => {
        items[items.length] = item
    }

    const hapusData = (index) => {
        delete items[index] // request ke api
        items = items.filter(Boolean) // request mengambil ulang data dari api
    }
</script>


<FormTambahUser on:tambahData={(e) => tambahData({
    name: e.detail.nama,
    email: e.detail.email,
    website: e.detail.website,
})}/>

<table class="table-auto">
    <thead>
        <tr>
            <th>No.</th>
            <th>Nama</th>
            <th>Email</th>
            <th>Website</th>
            <th>Action</th>
        </tr>
    </thead>
    <tbody>
       {#each items as item,index}
        <tr>
            <td>{index+1}</td>
            <td>{item.name}</td>
            <td>{item.email}</td>
            <td>{item.website}</td>
            <td>
                <a href="">edit</a>
                <button 
                on:click={() => hapusData(index)}
                class="bg-red-500 text-white px-4 py-2 rounded"
                >Hapus</button>
            </td>
        </tr>
       {/each} 
    </tbody>
</table>


<style>
    td,th {
        @apply p-4;
    }
</style>