<template>
  <div class="list-item">
    <label for="title" :aria-label="task.title">
      <input type="text" readonly :value="task.title" id="title" name="title" />
    </label>
  </div>
</template>
<script>
export default {
  name: 'TaskItem',
  props: {
    task: {
      type: Object,
      default: () => ({ id: '', state: '', title: '' }),
      validator: (task) => ['id', 'state', 'title'].every((key) => key in task)
    }
  }
}
</script>
