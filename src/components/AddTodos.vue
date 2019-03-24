<template>
  <div>
    <h3>Add Todos</h3>

    <div class="add">
      <form action @submit="onSubmit">
        <input type="text" name v-model="title" placeholder="Add Tod s">
        <input type="submit" value="Submit">
      </form>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "AddTodos",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit(e) {
      e.preventDefault();
      this.addTodo(this.title);
    }
  }
};
</script>

<style>
form {
  display: flex;
}
</style>
