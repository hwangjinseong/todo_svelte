<script lang="ts">
  import type { Task } from "../../model";
  import TodoItemActionButton from "./TodoItemActionButton.svelte";

  export let data: Task;
</script>

<div>
    <span spellcheck="false" contenteditable="true" bind:textContent={data.title}></span>
    <TodoItemActionButton on:delete on:edit/>
</div>

<style>
    div {
        display: flex;
        justify-content: space-between;
        border: 1px solid black;
        padding: 10px;
    }
</style>