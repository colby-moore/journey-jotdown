<template>
  <div id="app">
    <ExpensesComponent />
  </div>
</template>

<script>
import ExpensesComponent from "./components/ExpensesComponent.vue";

export default {
  name: "App",
  components: {
    ExpensesComponent
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
