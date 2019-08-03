<script>
import TodoItem from './TodoItem.svelte'
import uuid from 'uuid/v4'
export let listItems = []
let newTodoTitle = ''
let newTodoBody = ''
let errorMessage = ''



const addTodo = () => {
  if (!newTodoTitle || !newTodoBody) {
    let errorMessage = 'Please make sure to fill in the title and description'
    return;
  }
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
  padding: 15px;
  width: 200px;
  display: flex;
  justify-content:center;
  align-items: center;
  text-transform: uppercase;
  color: maroon;
  background-color: #EBD8D0;
  margin: auto;
  font-weight: 700;
  font-size: 20px;
  box-shadow: 0px 0px 1px 0px;
  cursor: pointer;
  transition: all 0.5s ease-in-out
}

.add-btn:active {
  background-color: maroon;
  color: #EBD8D0;
}
.add-btn:hover {
  background-color: maroon;
  color: #EBD8D0;
}

.input-label{
  color: maroon;
  font-weight: 700;
  font-size: 14px;
  padding-bottom: 5px;
}

.error-message {
  text-align: center;
  font-weight: 800;
  font-size: 16px;
  color: darkred;
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
  <label class="input-label">Title</label>
  <input type="text" class="new-todo-title" bind:value={newTodoTitle}/>
  <label class="input-label">Description</label>
  <textarea class="new-todo-body" bind:value={newTodoBody}></textarea>
  {#if errorMessage}
  <p class="error-message">{errorMessage}</p>
  {/if}
  <button class="add-btn" on:click={addTodo}> Add </button>
  <div class="todo-list-block">
  {#each listItems as todoItem}
  <TodoItem todo={todoItem}/>
  {/each}
  </div>
</div>
</div>
