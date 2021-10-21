<template>
  <div id="app">
    <ResumeEdit/>
  </div>
</template>

<script>
import ResumeEdit from "./components/ResumeEdit.vue"
export default {
  name: 'App',
  components:{
    ResumeEdit,
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
