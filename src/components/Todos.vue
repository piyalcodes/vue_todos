<template>
  <div>
    <h3>Todos</h3>
    <div
      @dblclick="onDblClick(todo)"
      v-for="todo in allTodos"
      class="todo"
      :key="todo.title"
      v-bind:class="{'is-complete':todo.completed}"
    >
      {{todo.title}}
      <span @click="deleteTodo(todo.id)" class="delete">X</span>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";

export default {
  name: "Todos",
  methods: {
    ...mapActions(["fetchTodos", "deleteTodo", "updateTodo"]),
    onDblClick(todo) {
      const updTodo = {
        id: todo.id,
        title: todo.title,
        completed: !todo.completed
      };
      this.updateTodo(updTodo);
    }
  },
  computed: mapGetters(["allTodos"]),
  created() {
    this.fetchTodos();
  }
};
</script>

<style>
.todo {
  background-color: aquamarine;
  border: 1px solid green;
  border-radius: 10px;
  padding: 10px;
  height: 100px;
  vertical-align: middle;
  width: 200px;
  display: inline-block;
  margin: 10px;
  text-align: center;
  box-sizing: border-box;
}
.delete {
  cursor: pointer;
}

.is-complete {
  background-color: blue;
}

@media (max-width: 500px) {
  .todo {
    grid-auto-columns: 1fr;
  }
}
</style>
