<template>
  <div class="tag-container">
    <span class="tag" v-for="tag in tags">
      <span class="tag-content">{{tag}}</span>
      <span class="close">X</span>
    </span>
    <input type="text" @keydown.enter="addTag">
    <div v-if="error" class="error">Bu etiket daha önceden eklenmiş!!</div>
  </div>
</template>
<script>
  export default {
    name: 'App',
    data() {
      return {
       tags:['deneme','deneme2'],
        error:false
      }
    },
    methods:{
      addTag(event){
      let value = event.target.value
      if(value.length > 0){
        if(this.tags.includes(value.toLowerCase())){
          this.error = true
          setTimeout(() =>{
            this.error = false
          }, 2000);

        }else{
          this.tags.push(value)
          this.error = false
          event.target.value = ''
        }
      }

      }
    }
  }
</script>
<style>

body{
  font-family: sans-serif;
}
.tag-container{
  border: 1px solid #ccc;
  padding: 20px;
}
input{
  outline: none;
  height: 30px;
  width: 100px;
}
.error{
  font-size: 12px;
  color:red;
  margin-top: 5px;
}

.tag{
  background-color: #fbbd08;
  padding: 10px;
  color: #000;
  cursor: default;
  margin-right: 10px;
}
.tag *{
  font-size: 14px;
}
.tag .close{
  font-size: 12px;
  font-weight: bold;
  cursor: pointer;
}

</style>