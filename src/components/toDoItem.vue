<template>
  <b-list-group-item>
    {{ toDo.text }}
  </b-list-group-item>
</template>

<script>
export default {
  name: "toDoItem",
  props: {
    toDo: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style>
</style>