<script>
    import { createEventDispatcher } from 'svelte';

    let dispatch = createEventDispatcher();

    let name;
    let power;

    let abilities = [];

    const handleSubmit = () => {
        console.log(name, power, abilities);
        const hero = {
            name: name,
            power: power,
            abilities: abilities,
            id: Math.random()
        }
        dispatch('addHero', hero)
    }
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <label>Power</label>
    <select bind:value={power}>
    <option value="Weak">Weak</option>
    <option value="Strong">Strong</option>
    <option value="Strongest">Strongest</option>
    </select>

    <label>Abilities</label>
    <input type="checkbox" bind:group={abilities} value="Super strength"> Super strength<br>
    <input type="checkbox" bind:group={abilities} value="Flight"> Flight<br>
    <input type="checkbox" bind:group={abilities} value="Invisibility"> Invisibility<br>
    <input type="checkbox" bind:group={abilities} value="Laser"> Laser<br>
    <button>Recruit hero</button>
</form>

<style>
</style>