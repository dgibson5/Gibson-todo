<script>
	import Todos from './Todos.svelte';
</script>

<main>
	<h1>My To-Do List</h1>
	<p>Keeping Track Is Tricky, Use a to do List to Manage Your Tasks. </p>
	<p>Enter Task In The Feild Below</p>
    <Todos />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #275346;
		text-transform: uppercase;
		font-size: 5em;
		font-weight: 100;
		font-family:'Segoe UI';
	}

	p {
		font-size: 1.5em;
		margin-bottom: 2em;
	}



	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>