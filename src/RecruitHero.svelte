<script>
    let name;
    let power;

    let abilities = [];

    const handleSubmit = () => {
        console.log(name, power, abilities);
    }
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="text" placeholder="power" bind:value={power}>
    <label>Abilities</label>
    <input type="checkbox" bind:group={abilities} value="Super strength"> Super strength<br>
    <input type="checkbox" bind:group={abilities} value="Flight"> Flight<br>
    <input type="checkbox" bind:group={abilities} value="Invisibility"> Invisibility<br>
    <input type="checkbox" bind:group={abilities} value="Laser"> Laser<br>
    <button>Recruit hero</button>
</form>

<style>
</style>