<script lang="ts">
  import NewTodoForm from "./NewTodoForm.svelte";
  import TodoItem from "./TodoItem.svelte";

  let todos: { id: number; text: string; completed: boolean }[] = [];

  function addTodo(text: string) {
    todos = [...todos, { id: todos.length + 1, text, completed: false }];
  }

  function deleteTodo(id: number) {
    todos = todos.filter((todo) => todo.id !== id);
  }
</script>

<h1 class="text-3xl font-bold mb-4">📝 To-Do-List 📒</h1>

<NewTodoForm {addTodo} />

<ul class="my-4">
  {#each todos as todo (todo.id)}
    <TodoItem {todo} onDelete={deleteTodo} />
  {/each}
</ul>
