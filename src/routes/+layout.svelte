<script>
	import '../app.postcss';
</script>

<ul>
	<li>
		<a href="/">Home</a>
	</li>
	<li>
		<a href="/users">User</a>
	</li>
</ul>

<slot />

<style>
	a {
		@apply text-blue-600;
	}
	a:hover {
		@apply text-blue-800;
	}
</style>
