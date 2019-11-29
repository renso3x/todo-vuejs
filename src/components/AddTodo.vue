<template>
  <div>
    <!-- bind submit event -->
    <form @submit="addTodo">
      <input
        type="text"
        name="title"
        v-model="title"
        placeholder="Add Todo..."
      />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
export default {
  name: 'AddTodo',
  data() {
    return {
      title: ''
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();

      const newTodo = {
        title: this.title,
        completed: false
      };
      // emit and event up to parent
      this.$emit('add-todo', newTodo);
      this.title = '';
    }
  }
};
</script>
