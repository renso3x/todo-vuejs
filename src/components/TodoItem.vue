<template>
  <!-- bind the styling -->
  <div v-bind:class="{'is-complete': todo.completed}">
    <p>
      <!-- this bind the method inside a component -->
      <input type="checkbox" v-on:change="markComplete" />
      {{ todo.name }}
      <!-- create send an event -->
      <button @click="$emit('del-todo', todo.id)">X</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style  scoped>
.is-complete {
  text-decoration: line-through;
}
</style>