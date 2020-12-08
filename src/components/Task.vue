<template>
<div>
  <span
      :class="{taskDone:taskToDisplay.isDone}"
      @click="$emit('end-task')">{{ taskToDisplay.message | enMajuscule }}</span><button @click="deleteTask">Supprimez</button>
</div>
</template>

<script>
import {enMajuscule} from "@/utils";

export default {
  name: "Task",
  props:{
    taskToDisplay:{
      type: Object,
      default: {
        message: "",
        isDone: false
      },
    },
  },
  methods:{
    deleteTask(){
      this.$emit("remove");
    }
  },
  filters:{
    enMajascule: enMajuscule
  }
}
</script>

<style scoped>
span{
  width: 50%;
  display: inline-block;
}
.taskDone{
  text-decoration: line-through;
  color: darkgrey;
}

</style>
