<script>
	let firstName = 'Captain';
	let lastName = 'Marvel';
	$: fullName = `${firstName.toUpperCase()} ${lastName.toUpperCase()}`;

	let heroes = [
		{ name : 'Captain Marvel', power : 'Great', id: 1 },
		{ name : 'Hawkeye', power : 'Average', id: 2 },
		{ name : 'Black widow', power : 'Good', id: 3 },
	];
</script>

<main>
	<h1>Hello {fullName}!</h1>
	
	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}>
	
	{#each heroes as hero (hero.id)}
	<h4>
	{hero.name}
	</h4>
	{:else}
		<p>The world has lost all hope</p>
	{/each}
	
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>