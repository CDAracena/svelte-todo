<script>
	import TodoList from './components/TodoList.svelte';
	export let name;
	const appTitle = "Svelte Todo App"

</script>

<style>
	h1 {
		color: maroon;
	}
	.container {
		display: flex;
		flex-direction: column;
	}
	.title-container {
		background-color: #EBD8D0;
		border-radius: 4px;
		flex: 1;
		text-align: center;
	}
</style>

<div class="container">
	<div class="title-container">
		<h1 class="title">{appTitle}</h1>
	</div>
	<div class="container-body">
		<TodoList/>
	</div>

</div>
