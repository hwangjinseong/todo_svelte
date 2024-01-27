<script lang="ts">
  import TodoItem from "./TodoItem.svelte"; 
  import type { Task } from "../model";

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

<div>
    {#each items as item}
    <TodoItem data={item} />
    {/each}
</div>

<style>
    div {
        display: flex;
        flex-direction: column;
        gap: 15px;
    }
</style>