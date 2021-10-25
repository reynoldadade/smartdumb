<!-- Please remove this file from your project -->
<template>
  <div
    class="w-full p-2 rounded flex justify-between border border-gray-400 m-2"
  >
    <span>
      {{ task.name }}
    </span>
    <span>
      <button class="text-red-500" @click.prevent="removeTask(task)">
        <i class="fas fa-trash"></i>
      </button>
    </span>
  </div>
</template>

<script>
export default {
  props: {
    task: {
      type: Object,
      default: () => {},
    },
    removeTask: {
      type: Function,
      default: () => {},
    },
  },
}
</script>

<style></style>
