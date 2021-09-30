<template>
  <div>
    <b-container>
      <b-row>
        <b-col>
          <toDoList />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import toDoList from "@/components/toDoList.vue";
export default {
  name: "App",
  components: {
    toDoList,
  },
};
</script>

<style>
.container {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.card-header {
  text-align: center;
}
</style>
