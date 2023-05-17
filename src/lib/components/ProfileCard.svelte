<script>
    export let name = "Binsar"
    export let email = "binsarjr121@gmail.com"
    export let bgColor = '';
    export let imgSrc = ''
</script>


<div class="p-4 border rounded {bgColor}">
    {#if imgSrc}
    <img src={imgSrc} alt="">
    {/if}
	<h2 class="text-lg">{name}</h2>
	<p class="text-gray-500">{email}</p>
</div>
