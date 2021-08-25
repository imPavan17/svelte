<script>
	let people = [
		{ name: "John", age: 25, id: 1, beltColor: 'black' },
		{ name: "Yoshi", age: 26, id: 2, beltColor: 'red' },
		{ name: "Cena", age: 29, id: 3, beltColor: 'brown' }
	];
</script>

<main>
	<!-- key is passed inside () -->
	{#each people as person (person.id)} 
		<div>
			<h4>{person.name} - {person.age} years old, {person.beltColor} belt.</h4>
		</div>	
		{:else}
		<p>There are no people.</p>
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