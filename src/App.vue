<template>
   <div class="container">
       <Tags v-model="tags" :color="'primary'" />
     {{tags}}
     <Tags v-model="tags2" :color="'secondary'"/>
     {{tags2}}
     <Tags v-model="tags3" :color="'info'"/>
     {{tags3}}
     <Tags v-model="tags4" :color="'danger'"/>
     {{tags4}}
     <Tags v-model="tags5" :color="'success'"/>
     {{tags5}}
     <Tags v-model="tags6" :color="'warning'"/>
     {{tags6}}
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
        tags2:'kalvye,mouse',
        tags3:'ev,araba',
        tags4:'musluk,şişe',
        tags5:'çay,kahve',
        tags6:'boya,kutu',
      }
    }
  }
</script>
<style>
body{
  font-family: sans-serif;
}
</style>