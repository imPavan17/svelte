<script>
	let firstName = "John";
	let lastName = 'Cena';
	let beltColor = 'black';

	/** Reactive values - Which are reactive, they update automatically, when the data they depend on changes. It watches certain values and update in the FE.*/
	$: fullName = `${firstName} - ${lastName}`; 
	$: console.log(beltColor) // Reactive statements
	/** We can also include multiple reactive statements*/
	$: {
		console.log(beltColor);
		console.log(fullName);
	}
</script>

<main>
	<p>{fullName} - {beltColor} belt</p>
	<input type="text" bind:value={firstName}/>
	<input type="text" bind:value={lastName}/>
	<input type="text" bind:value={beltColor}/>
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