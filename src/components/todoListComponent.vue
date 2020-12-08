<template>
  <div>
    <input ref="myInput" type="text" v-model="currentTask" @keypress.enter="addTask">
    <button @click="addTask">Ajouter une tâche</button>
    <button @click="removeTask">Supprimer une tâche</button>
    <ul>
      <Task
          :key="i"
          v-for="(task, i) in tasks"
          :taskToDisplay="task"
          @remove="removeTask(i, task.id)"
          @done="taskDone(task)"
      />
    </ul>
  </div>
</template>

<script>
import Task from "@/components/Task";
import Axios from "axios";
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
      Axios.post("https://todo-hoc.dunarr.com/5fcf79796cf7f",({
        name: this.currentTask,
        isDone: false
      }))
      this.tasks.push(response.data)
      this.currentTask = ""
      this.$refs.myInput.focus()
    },
    removeTask(index, id){
      Axios.delete("https://todo-hoc.dunarr.com/5fcf79796cf7f" + id)
      this.tasks.splice(index,1)
    },
    async fetchTask(){
      const response = await Axios.get("https://todo-hoc.dunarr.com/5fcf79796cf7f")
      this.tasks = response.data.tasks
    },
    taskDone(task){
      const Done = !task.isDone
      Axios.put("https://todo-hoc.dunarr.com/5fcf79796cf7f" + task.id,{
        isDone: Done
      })
      task.isDone = true
    },
    mounted(){
      this.fetchTask()
    }
  }
}
</script>

<style scoped>

</style>
