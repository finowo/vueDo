<template>
  <div>
    <b-card header="To-Do List" header-tag="header">
      <b-list-group>
        <toDoItem v-for="item in list" :key="item.id" :toDo="item" />
      </b-list-group>
      <template v-slot:footer>
        <b-button class="float-end" varient="primary">Add</b-button>
      </template>
    </b-card>
  </div>
</template>

<script>
import toDoItem from "@/components/toDoItem.vue";

export default {
  name: "toDoList",
  components: {
    toDoItem,
  },
  data() {
    return {
      list: [
        { id: 1, text: "Eat the Cat", done: false },
        { id: 2, text: "Clean the House", done: true },
        { id: 3, text: "Hoover the bedroom", done: false },
      ],
    };
  },
};
</script>

<style>
</style>
