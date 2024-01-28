<script lang="ts">
  import TodoItems from "./components/TodoItems.svelte";
  import type { Task } from "./model";

  let items: Task[] = [
    {
        id: "1",
        title: "할일1",
        completed: false
    },
    {
        id: "2",
        title: "할일2",
        completed: false
    },
    {
        id: "3",
        title: "할일3",
        completed: false
    }
  ]

</script>

<h1>TodoList</h1>
  
<TodoItems bind:items={items}/>

