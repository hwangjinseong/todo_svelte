<script lang="ts">
    export let visible = true

    function onClose() {
        visible = false
    }
</script>

{#if visible}
    <div class="modal-bg" on:click={onClose}>
        <div class="modal" on:click|stopPropagation>
            <slot/>
        </div>
    </div>
{/if}

<style>
    .modal-bg {
        position: fixed; 
        z-index: 99; 
        left: 0;
        top: 0;
        width: 100%; 
        height: 100%; 
        overflow: auto; 
        background-color: rgb(0,0,0);
        background-color: rgba(0,0,0,0.4);
    }

    .modal {
        background-color: #fefefe;
        margin: 15% auto; 
        padding: 20px;
        border: 1px solid #888;
        width: 80%;
    }
</style>