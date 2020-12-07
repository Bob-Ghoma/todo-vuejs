<template>
<div>
  <h1>{{ message }}</h1>
</div>
</template>

<script>
export default {
  name: "HelloComponent",
  data(){
    return {
      name: "",
    };
  },
  computed: {
    message(){
      if (this.name){
        return "Transfére de" + this.name
      }
    }
  }
}
</script>

<style scoped>

</style>
