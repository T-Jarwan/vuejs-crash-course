<template>
  <div :key="task.id" v-for="task in tasks">
    <TaskComponent
      @delete-task="$emit('delete-task', task.id)"
      @toggle-reminder="$emit('toggle-reminder', task.id)"
      :task="task"
    />
  </div>
</template>

<script>
import TaskComponent from "./Task";
export default {
  name: "TasksComponent",
  components: { TaskComponent },
  props: {
    tasks: Array,
  },
  emits: ["delete-task", "toggle-reminder"],
};
</script>