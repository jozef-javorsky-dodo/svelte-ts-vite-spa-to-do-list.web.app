<script lang="ts">
  export let todo: { id: number; text: string; completed: boolean };
  export let onDelete: (id: number) => void;

  function handleToggle(event: Event) {
    todo.completed = (event.target as HTMLInputElement).checked;
  }

  function handleDeleteClick() {
    onDelete(todo.id);
  }
</script>

<li class="flex items-center py-2">
  <input type="checkbox" checked={todo.completed} on:change={handleToggle} />
  <span class:line-through={todo.completed} class="ml-2">{todo.text}</span>
  <button
    on:click={handleDeleteClick}
    class="ml-auto bg-red-500 hover:bg-red-700 text-white font-bold py-1 px-2 rounded"
  >
    Delete
  </button>
</li>
