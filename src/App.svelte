<script>
	// import ReactiveValues from './concepts/ReactiveValues.svelte';
	// import Loops from './concepts/Loops.svelte';
	// import InlineEventHandlers from './concepts/InlineEventHandlers.svelte';
	// import Conditionals from './concepts/Conditionals.svelte';

	import Modal from './Modal.svelte';

	let showModal = false;

	const toggleModal = () => {
		showModal = !showModal;
	}
</script>

<!-- <ReactiveValues /> -->
<!-- <Loops /> -->
<!-- <InlineEventHandlers /> -->
<!-- <Conditionals /> -->

<Modal {showModal} on:click={toggleModal}>
	<h2>Add new person.</h2>
	<form>
		<input type="text" placeholder="Name"/>
		<input type="text" placeholder="Belt Color"/>
	</form>
</Modal>
<button on:click={toggleModal}>Open</button>