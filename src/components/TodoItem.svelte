<script>
export let todo
console.log(todo)
export let deleteTodo
</script>
<style>
.todo-item-container {
  margin-bottom:20px;
  margin-top: 20px;
  display: flex;
  border-radius: 4px;
  padding: 10px;
  transition: background-color 0.5s ease-in-out;
}

.todo-item-container:hover{
  background-color: #ffffff80;

}
.todo-item-title {
  font-size: 14px;
  border-bottom: 1px solid #80000061;
  color: maroon;
  padding-bottom: 5px;
  font-size: 24px;
  text-transform: uppercase;
  font-weight: 700;
}

.todo-item-body {
  color: #333;
  padding-top: 10px;
  font-size: 18px;
  word-break: break-word;
}

.todo-item-titlebody {
  flex: 1;
}
.delete-container {
  display: flex;
  align-items: center;
  margin-left: 10px;
  background-color: red;
  padding-left: 5px;
  padding-right: 5px;
  border-radius: 4px;
  height: 50px;
  transition: all 0.5s ease-in-out;
  cursor: pointer;
  color: white;
}

.delete-container:hover {
  box-shadow: 0px 0px 2px 1px black;
}
</style>
<div class="todo-item-container">
  <div class="todo-item-titlebody">
    <div class="todo-item-title">{todo.title}</div>
    <div class="todo-item-body">{todo.body}</div>
  </div>
  <div class="delete-container" on:click={deleteTodo}>
  DELETE
  </div>
</div>
