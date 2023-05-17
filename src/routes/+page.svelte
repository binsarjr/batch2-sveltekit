<script>
	import ProfileCard from '$lib/components/ProfileCard.svelte';
	import AvatarImg from '$lib/assets/avatar.png';
	import Counter from '../lib/components/Counter.svelte';
	import Collapse from '../lib/components/Collapse.svelte';
	import Card from '../lib/components/Card.svelte';

	const onDecrement = () => {
		console.log('data saat ini berkurang');
	};
</script>

<a href="/">hello word</a>

<div class="container mx-auto my-5">
	<h1 class="text-2xl">ProfileCard</h1>
	<div class="grid grid-cols-5 gap-5">
		<ProfileCard />
		<ProfileCard name="Tian" email="tian@gmail.com" />
		<ProfileCard bgColor="bg-red-500" />
		<ProfileCard imgSrc="https://www.w3schools.com/howto/img_avatar.png" />
		<ProfileCard imgSrc={AvatarImg} />
		<ProfileCard />
		<ProfileCard />
	</div>

	<h2 class="text-2xl mt-4">Counter</h2>
	<Counter
		on:decrement={onDecrement}
		on:increment={(e) => {
			console.log('data bertambah sekarng menjadi', e.detail);
		}}
	/>

	<Card>
		asdasdsadasd
	</Card>
</div>
