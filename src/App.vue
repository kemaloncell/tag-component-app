<template>
   <div class="container">
       <Tags v-model="tags" />
     {{tags}}
   </div>
</template>
<script>
import Tags from './components/Tags.vue'
  export default {
    name: 'App',
    components: {
      Tags
    },
    data(){
      return{
        tags:'test,test2'
      }
    }
  }
</script>
<style>
body{
  font-family: sans-serif;
}
</style>