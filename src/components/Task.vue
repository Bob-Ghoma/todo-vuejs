<template>
<div>
  {{ taskToDisplay }}
  <button @click="deleteTask">Supprimez</button>
</div>
</template>

<script>
export default {
  name: "Task",
  props:{
    taskToDisplay:{
      type: String,
      default: ""
    },
  },
  methods:{
    deleteTask(){
      this.$emit("remove")
    }
  },

}
</script>

<style scoped>

</style>
