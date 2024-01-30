<script lang="ts">
  import type { Task } from "../../model";
  import TodoItem from "./TodoItem.svelte"; 

  export let items: Task[]

  function onDelete(task: Task) {
    items = items.filter((item: Task) => item.id != task.id)
  }
</script>

<div>
    {#each items as item}
    <TodoItem data={item} on:delete={() => onDelete(item)}/>
    {/each}
</div>

<style>
    div {
        display: flex;
        flex-direction: column;
        gap: 15px;
    }
</style>