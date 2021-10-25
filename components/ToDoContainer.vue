<template>
  <div class="w-full">
    <ToDoComponent
      v-for="todo in tasks"
      :key="todo.id"
      :task="todo"
      :remove-task="removeTask"
    />
    <div class="p-2">
      <input
        v-model="task"
        type="text"
        class="w-full h-full p-2"
        placeholder="Enter task here"
        @keydown.enter="addTask(task)"
      />
    </div>
  </div>
</template>

<script>
import ToDoComponent from '~/components/Todo.vue'
export default {
  components: {
    ToDoComponent,
  },
  data() {
    return {
      task: '',
      tasks: [],
    }
  },
  methods: {
    addTask(task) {
      // use date as id
      const newTask = { name: task, id: Date.now() }
      this.tasks = [...this.tasks, newTask]
    },
    removeTask(task) {
      // filter by id
      this.tasks = this.tasks.filter((item) => item.id !== task.id)
    },
  },
}
</script>

<style></style>
