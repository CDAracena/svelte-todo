<script>
import uuid from 'uuid/v4'
export let listItems = []
let newTodoTitle = ''
let newTodoBody = ''



const addTodo = () => {
  const newTodo = {
    id: uuid(),
    title: newTodoTitle,
    body: newTodoBody
  }
  newTodoTitle = ''
  newTodoBody = ''

  listItems = [...listItems, newTodo]
  console.log(listItems)
}

console.log(listItems)

</script>
<style>

.main-container {
  display: flex;
  flex-direction: column;
}

.new-todo-container {
  display: flex;
  flex-direction: column;
  flex: 1;

}

.new-todo-title {
  width: 350px;
  border-radius: 4px;
  outline-color: maroon;
}

.new-todo-body {
  border-radius: 4px;
  outline-color: maroon;
}

.add-btn {
  padding: 20px;
  width: 200px;
  display: flex;
  justify-content:center;
  align-items: center;
  text-transform: uppercase;
  background-color: #EBD8D0;
  margin: auto;
}

</style>
<div class="main-container">
<div class="todo-list-container">
  {#if listItems.length >= 1}
<h3> Awesome, you have {listItems.length} {listItems.length > 1 ? 'todos' : 'todo'}</h3>
  {:else}
<h3>Seems like you haven't added any todos yet... </h3>
  {/if}
</div>

<div class="new-todo-container">
  <input type="text" class="new-todo-title" bind:value={newTodoTitle}/>
  <textarea class="new-todo-body" bind:value={newTodoBody}></textarea>
  <button class="add-btn" on:click={addTodo}> Add </button>
</div>
</div>
