<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      v-show="homePage"
      @btn-click="this.$emit('toggle-add-task')"
      :text="showAddTask ? 'Close' : 'Add Task'"
      :color="showAddTask ? 'red' : 'green'"
    />
  </header>
</template>

<script>
import Button from "./Button";

export default {
  name: "HeaderComponent",
  components: { Button },
  props: {
    title: String,
    showAddTask: Boolean,
  },
  emits: ["toggle-add-task"],
  computed: {
    homePage() {
      return this.$route.path === "/";
    },
  },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>