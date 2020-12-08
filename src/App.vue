<template>
  <div id="app">
    <Banner></Banner>
    <TodoListComponent/>

    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import Banner from "@/components/Banner";
import HelloWorld from './components/HelloWorld.vue'
import TodoListComponent from "@/components/todoListComponent";
import HelloComponent from "@/components/HelloComponent";
import TestComponent from "@/components/TestComponent";
import Task from "@/components/Task";

export default {
  name: 'App',
  components: {
    Task,
    Banner,
    TestComponent,
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
