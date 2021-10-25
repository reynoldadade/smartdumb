<!-- Please remove this file from your project -->
<template>
  <div class="w-full p-2 rounded flex justify-between">
    <span>
      {{ task.name }}
    </span>
    <span>
      <button class="text-red-500"><i class="fas fa-trash"></i></button>
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
