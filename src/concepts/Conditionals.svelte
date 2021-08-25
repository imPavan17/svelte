<script>
	let people = [
		{ name: "John", age: 25, id: 1, beltColor: 'black' },
		{ name: "Yoshi", age: 26, id: 2, beltColor: 'red' },
		{ name: "Cena", age: 29, id: 3, beltColor: 'brown' }
	];
	const handleClick = (id) => {
		// We should reassign to update in the FE.
		people = people.filter(person => person.id !== id);
	}

    let num = 6;
</script>

{#if num > 20} 
    <p>Greater than 20.</p>
{:else if num > 5}
    <p>Greater than 5.</p>
{:else}
    <p>Not greater than 5.</p>
{/if}

<main>
	<!-- key is passed inside () -->
	{#each people as person (person.id)} 
		<div>
			<h4>
                {person.name} - {person.age} years old, {person.beltColor} belt.
                {#if person.beltColor === 'black'}
                    <strong>(MASTER)</strong>
                {/if}
            </h4>
			<button on:click={() => handleClick(person.id)}>Delete</button>
		</div>	
		{:else}
		<p>There are no people..</p>
	{/each}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}
	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>