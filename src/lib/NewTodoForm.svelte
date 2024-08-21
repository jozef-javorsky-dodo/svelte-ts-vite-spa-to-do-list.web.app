<script lang="ts">
  export let addTodo: (text: string) => void;
  let newTodo = "";

  function handleSubmit() {
    if (newTodo.trim() !== "") {
      addTodo(newTodo.trim());
      newTodo = "";
    }
  }
</script>

<form on:submit|preventDefault={handleSubmit} class="flex items-center mb-4">
  <input
    type="text"
    bind:value={newTodo}
    placeholder="Add a new to-do note."
    class="border border-gray-400 rounded-l p-2 flex-grow"
  />
  <button
    type="submit"
    class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-r"
  >
    Add
  </button>
</form>
