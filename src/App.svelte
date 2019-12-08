<script>
	export let name;
	const appTitle = "Svelte Todo App"
	import TodoList from './components/TodoList.svelte'
</script>

<style>
	h1 {
		color: maroon;
	}
	.container {
		padding: 20px;
		max-width: 1024px;
	}
</style>

<div class="container">
<h1 class="title">{appTitle}</h1>
<TodoList/>
</div>
