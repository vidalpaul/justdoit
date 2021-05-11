<script>
	let todos = [];
	function addTodo() {
		todos = [...todos, ''];
	}
	function removeSelf(index){
	todos = [...todos.slice(0, index), ...todos.slice(index+1)];
	}
</script>

<main>
	<h1><b>Just Do It! &#9994</b></h1>
	{#each todos as todo, index}
	<input bind:value={todos[index]}>
	<button on:click={()=>
		removeSelf(index)}>&#9989</button>
	<br>
	{/each}
	<button on:click={addTodo}>&#10133 Task</button>
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
		font-weight:bold;
		text-transform: uppercase;
		font-size: 2em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>