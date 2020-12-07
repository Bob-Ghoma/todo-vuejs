<template>
  <div id="app">
    <HelloComponent/>
    <todo-list-component/>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TodoListComponent from "@/components/todoListComponent";
import HelloComponent from "@/components/HelloComponent";

export default {
  name: 'App',
  components: {
    HelloComponent,
    TodoListComponent,
    HelloWorld
  }
}
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
