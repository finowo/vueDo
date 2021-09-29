<template>
  <div>
    <b-card header="To-Do List" header-tag="header">
      <template v-slot:footer>
        <b-button class="float-end" varient="primary">Add</b-button>
      </template>
    </b-card>
    <ol>
      <li>Todo item 1</li>
      <li>Todo item 2</li>
      <li>Todo item 3</li>
    </ol>
  </div>
</template>

<script>
export default {
  name: "toDoList",
  components: {},
};
</script>

<style>
</style>
