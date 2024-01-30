<script lang="ts">
  import TodoItemCreate from "./components/TodoItemCreate.svelte";
  import TodoItems from "./components/TodoItems.svelte";
  import type { Task } from "./model";

  let items: Task[] = []

</script>

<h1>TodoList</h1>
  
<TodoItems bind:items={items}/>

<TodoItemCreate bind:items={items}/>