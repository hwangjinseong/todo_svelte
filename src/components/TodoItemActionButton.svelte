<script>
  import { createEventDispatcher } from "svelte";

    const dispatch = createEventDispatcher()

    function onDelete() {
        dispatch('delete')
    }
</script>

<div>
    <button>수정</button>
    <button on:click={onDelete}>삭제</button>
</div>

<style>
    div {
        display: flex;
        gap: 10px;
    }
</style>