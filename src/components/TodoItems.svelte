<script lang="ts">
  import TodoItem from "./TodoItem.svelte"; 
  import type { Task } from "../model";

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