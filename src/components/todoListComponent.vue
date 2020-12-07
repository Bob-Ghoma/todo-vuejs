<template>
  <div>
    <h1> {{ message }}</h1>
    <input type="text" v-model="currentTask" @keypress.enter="addTask">
    <button @click="addTask">Ajouter un joueur</button>

    <ul>
      <Task :key="i" v-for="(task, i) in tasks" :taskToDisplay="task" @remove="removeTask(i)"/>
    </ul>

  </div>
</template>

<script>
import Task from "@/components/Task";
export default {
name: "todoListComponent",
  components: {Task},
  data(){
  return {
    currentTask: "",
    tasks: []
   }
  },
  props: {
    message: {
     type: String,
      default: "Liste des tâches",
    }
  },
  methods: {
    addTask(){
      this.tasks.push(this.currentTask);
      this.currentTask = ""
    },
    removeTask(index){
      this.tasks.splice(index,1)
    }
  }
}
</script>

<style scoped>

</style>
