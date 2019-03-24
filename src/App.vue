<template>
  <div id="app">
    <AddTodos/>
    <FilterTodos/>
    <Todos/>
  </div>
</template>

<script>
import Todos from "./components/Todos.vue";
import AddTodos from "./components/AddTodos.vue";
import FilterTodos from "./components/FilterTodos.vue";

export default {
  name: "app",
  components: {
    Todos,
    AddTodos,
    FilterTodos
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
