<template>
  <div>
    Filter Todos
    <section>
      <select @change="filterTodos($event)">
        <option value="200">200</option>
        <option value="100">100</option>
        <option value="50">50</option>
        <option value="40">40</option>
        <option value="2">2</option>
      </select>
    </section>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: "FilterTodos",
  methods: mapActions(["filterTodos"])
};
</script>

<style>
</style>
