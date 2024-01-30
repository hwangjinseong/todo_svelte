<script lang="ts">
  import { createEventDispatcher } from "svelte";
  import type { Task } from "../../model";
  import TodoItem from "./TodoItem.svelte"; 

  export let items: Task[]

  const dispatch = createEventDispatcher()

  function onDelete(task: Task) {
    items = items.filter((item: Task) => item.id != task.id)
  }
</script>

<div>
    {#each items as item}
    <TodoItem data={item} 
    on:edit={() => dispatch('edit', item)}
    on:delete={() => onDelete(item)}/>
    {/each}
</div>

<style>
    div {
        display: flex;
        flex-direction: column;
        gap: 15px;
    }
</style>