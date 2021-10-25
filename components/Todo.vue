<!-- Please remove this file from your project -->
<template>
  <div
    class="w-full p-2 rounded flex justify-between border border-gray-400 m-2"
    :class="{ 'bg-green-300': task.completed }"
  >
    <span>
      {{ task.name }}
    </span>
    <div>
      <span class="p-2">
        <button
          class="text-blue-500"
          @click.prevent="markAsCompletedEvent(task)"
        >
          <i class="fas fa-check"></i>
        </button>
      </span>
      <span class="p-2">
        <button class="text-red-500" @click.prevent="removeTaskEvent(task)">
          <i class="fas fa-trash"></i>
        </button>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    task: {
      type: Object,
      default: () => {},
    },
  },
  methods: {
    removeTaskEvent(task) {
      this.$emit('removeTask', task)
    },
    markAsCompletedEvent(task) {
      this.$emit('markAsCompleted', task)
    },
  },
}
</script>

<style></style>
