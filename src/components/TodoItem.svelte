<script lang="ts">
  import TodoItemActionButton from "./TodoItemActionButton.svelte";
  import type { Task } from "../model";

  export let data: Task;
</script>
<div>
    <span>{data.title}</span>
    <TodoItemActionButton on:delete/>
</div>

<style>
    div {
        display: flex;
        justify-content: space-between;
        border: 1px solid black;
        padding: 10px;
    }
</style>