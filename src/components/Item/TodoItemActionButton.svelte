<script>
  import { createEventDispatcher } from "svelte";

    const dispatch = createEventDispatcher()

    function onEdit() {
        dispatch('edit')

    }

    function onDelete() {
        dispatch('delete')
    }
</script>

<div>
    <button on:click={onEdit}>수정</button>
    <button on:click={onDelete}>삭제</button>
</div>

<style>
    div {
        display: flex;
        gap: 10px;
    }
</style>