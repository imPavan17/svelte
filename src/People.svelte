<script>
	import Modal from './Modal.svelte';
	import AddPerson from './AddPerson.svelte';

	let showModal = false;

	let people = [
		{ name: "John", age: 25, id: 1, beltColor: 'black' },
		{ name: "Yoshi", age: 26, id: 2, beltColor: 'red' },
		{ name: "Cena", age: 29, id: 3, beltColor: 'brown' }
	];

    const addPerson = ({ detail }) => {
        people = [detail, ...people];
        showModal = !showModal;
    };

    const handleDelete = (id) => {
        people = people.filter(person => person.id !== id);
    };

	const toggleModal = () => {
		showModal = !showModal;
	};
</script>

<main>
	<Modal {showModal} on:click={toggleModal}> 
		<AddPerson on:addPerson={addPerson}/>
	</Modal>

	<!-- key is passed inside () -->
	{#each people as person (person.id)} 
		<div>
			<h4>
                {person.name} - {person.age} years old, {person.beltColor} belt.
                {#if person.skills}
                    Skills - ({person.skills.join(', ')})
                {/if}
                <a href="#!" on:click={() => handleDelete(person.id)}>Delete</a>
            </h4>
		</div>	
		{:else}
		<p>There are no people.</p>
	{/each}

	<button on:click={toggleModal}>Open</button>

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