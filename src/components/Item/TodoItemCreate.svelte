<script lang="ts">
  import { v4 as uuidv4 } from 'uuid';
  import type { Task } from '../../model';

    export let items: Task[];

    let title = "";

    function onKeydown(e: KeyboardEvent) {
        if(e.key != "Enter") return
        if(title === "") return

        items = [...items, {
            id: uuidv4(),
            title,
            completed: false
        }]

        title = "";
    }
</script>

<input type='text' bind:value={title} on:keydown={onKeydown} placeholder="입력"/> 

<style>
    input {
        width: 100%;
        padding: 10px;
        margin-top: 15px;
        font-size: 16px;
        box-sizing: border-box;
    }
</style>