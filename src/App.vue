<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld />

  <Clock />
  <br />
  <br />
  <Table />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Table from "./components/Table.vue";
import Clock from "./components/Clock.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    Table,
    Clock,
  },
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
