<script>
    let name;
    let power;

    const handleSubmit = () => {
        console.log(name, power);
    }
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="text" placeholder="power" bind:value={power}>
    <button>Recruit hero</button>
</form>

<style>
</style>