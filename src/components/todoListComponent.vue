<template>
  <div>
    <input ref="myInput" type="text" v-model="currentTask" @keypress.enter="addTask">
    <button @click="addTask">Ajouter un joueur</button>
    <ul>
      <Task
          :key="i"
          v-for="(task, i) in tasks"
          :taskToDisplay="task"
          @remove="removeTask(i)"
          @end-task="task.isDone = true"
      />
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
    tasks: [],
    currentTask: ""
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
      this.tasks.push({
          message: this.currentTask,
          isDone: false
    })

    },
    removeTask(index){
      this.tasks.splice(index,1)
    }
  }
}
</script>

<style scoped>

</style>
