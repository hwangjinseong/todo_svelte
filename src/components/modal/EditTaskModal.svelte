<script lang="ts">
  import { createEventDispatcher } from "svelte";
  import type { Task } from "../../model";
  import Modal from "./Modal.svelte";

  export let data: Task | null

  const dispatch = createEventDispatcher()

  let visible = false

  function onClose() {
    visible = false
  }

  function onSave() {
    dispatch('save', data)
    onClose()
  }
</script>


<Modal bind:visible={visible}>
    <h1>Edit task</h1>
    <input type="text" bind:value={data.title}/>
    <button on:click={onSave}>완료</button>
    <button on:click={onClose}>닫기</button>
</Modal>