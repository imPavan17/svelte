<script>
    import { createEventDispatcher } from 'svelte';

    let dispatch = createEventDispatcher();

    let name = "";
    let beltColor = "";
    let age = 0;

    let skills = [];

    const handleSubmit = () => {
        const person = { id: Math.random(), name, beltColor, age, skills };
        dispatch('addPerson', person);
    }
</script>

<div>
    <h2>Add new person.</h2>
	<form on:submit|preventDefault={handleSubmit}>
		<input type="text" placeholder="Name" bind:value={name}/>
        <input type="number" placeholder="Age" bind:value={age}/>
        <label>Skills</label>
        <!-- <input type="checkbox" bind:checked={fighting}/>Fightings<br>
        <input type="checkbox" bind:checked={sneaking}/>Sneaking<br>
        <input type="checkbox" bind:checked={running}/>Running<br> -->

        <input type="checkbox" bind:group={skills} value="fighting"/>Fightings<br>
        <input type="checkbox" bind:group={skills} value="sneaking"/>Sneaking<br>
        <input type="checkbox" bind:group={skills} value="running"/>Running<br>

        <label>Belt Color</label>
        <select bind:value={beltColor}>
            <option value="black">Black</option>
            <option value="orange">Orange</option>
            <option value="brown">Brown</option>
            <option value="white">White</option>
        </select>
        <button>Add Person</button>
	</form>
</div>

<style>

</style>