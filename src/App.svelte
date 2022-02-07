<script>
	let firstName = 'Captain';
	let lastName = 'Marvel';
	let fullName = `${firstName.toUpperCase()} ${lastName.toUpperCase()}`;
</script>

<main>
	<h1>Hello {fullName}!</h1>
	
	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}>
	
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