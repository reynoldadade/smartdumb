<template>
  <div class="w-1/2">
    <div class="p-2 font-semibold">Smart vs Dumb components</div>
    <div class="w-full shadow p-2 rounded border">
      <ToDoComponent
        v-for="todo in tasks"
        :key="todo.id"
        :task="todo"
        @removeTask="removeTask"
        @markAsCompleted="markAsCompleted"
      />
      <div class="p-2">
        <input
          v-model="task"
          type="text"
          class="w-full h-full p-2 border rounded border-blue-300"
          placeholder="Enter task here"
          @keydown.enter="addTask(task)"
        />
      </div>
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
      const newTask = { name: task, id: Date.now(), completed: false }
      this.tasks = [...this.tasks, newTask]
    },
    removeTask(task) {
      // filter by id
      this.tasks = this.tasks.filter((item) => item.id !== task.id)
    },
    markAsCompleted(task) {
      const completedTask = { ...task, completed: true }
      const filteredTasks = this.tasks.filter((item) => item.id !== task.id)
      this.tasks = [...filteredTasks, completedTask]
    },
  },
}
</script>

<style></style>
