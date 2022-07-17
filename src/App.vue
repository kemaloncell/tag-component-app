<template>
   <div class="container">
       <Tags v-model="tags" />
     {{tags}}

     <Tags v-model="tags2" />
     {{tags2}}
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
        tags:'defter,kitap',
        tags2:'kalvye,mouse'
      }
    }
  }
</script>
<style>
body{
  font-family: sans-serif;
}
</style>