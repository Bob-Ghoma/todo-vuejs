<template>
  <div>
    <h1 v-if="name"> {{ name }}</h1>
    <input type="text" v-model="name">
    <slot></slot>
  </div>

</template>

<script>
import todoListComponent from "@/components/todoListComponent";
export default {
  name: "TestComponent",
  data(){
    return {
      name: "Nom"
    };
  }
};
</script>

<style scoped>

</style>
