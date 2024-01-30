<script lang="ts">
  import TodoItemCreate from "./components/Item/TodoItemCreate.svelte";
  import TodoItems from "./components/Item/TodoItems.svelte";
  import EditTaskModal from "./components/modal/EditTaskModal.svelte";
  import type { Task } from "./model";

  let items: Task[] = []

  let editTaskModalVisible = false
  let editTaskModalData: Task | null = null

  function onTaskEdit(e) {
    editTaskModalData = structuredClone(e.detail) ?? null
    editTaskModalVisible = true
  }

  function onTaskEditSave(e) {
    items = items.map((item: Task) => item.id === e.detail.id ? e.detail : item)
    
  }
</script>

<EditTaskModal visible={editTaskModalVisible} data={editTaskModalData} on:save={onTaskEditSave}/>
<TodoItems bind:items={items} on:edit={onTaskEdit}/>
<TodoItemCreate bind:items={items}/>