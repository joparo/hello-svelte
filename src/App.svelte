<script>

	import Modal from './Modal.svelte';
	import RecruitHero from './RecruitHero.svelte';

	let firstName = 'Captain';
	let lastName = 'Marvel';
	$: fullName = `${firstName.toUpperCase()} ${lastName.toUpperCase()}`;

	let heroes = [
		{ name : 'Captain Marvel', power : 'Great', id: 1 },
		{ name : 'Hawkeye', power : 'Average', id: 2 },
		{ name : 'Black widow', power : 'Good', id: 3 },
	];

	const removeHero = (id) => {
		heroes = heroes.filter(hero => hero.id != id);
	}

	let showModal = false;

	const toggleModal = () => {
		showModal = !showModal;
	}
</script>

<Modal showModal={showModal} message="The world needs more heroes" on:click={toggleModal}>
	<h3 slot=title>Recruit your hero!</h3>
	<RecruitHero/>
</Modal>


<main>
	<h1>Hello {fullName}!</h1>
	
	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}>
	
	{#each heroes as hero (hero.id)}
	<h4>
	{hero.name}
	</h4>
	<button on:click="{() => heroes = heroes.filter(h => hero.id != h.id)}">Remove</button>
	{:else}
		<p>The world has lost all hope</p>
	{/each}
	
	{#if heroes.length > 2}
        <p>We can still fight Thanos</p>
    {:else if heroes.length > 1}
        <p>We can try to fight Thanos</p>
	{:else}
		<p>We are doomed</p>
    {/if}

	<button on:click={toggleModal}>Recruit a new hero</button>

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