<template>
  <div class="tag-container">
    <span class="tag" v-for="tag in tags">
      <span class="tag-content">{{tag}}</span>
      <span class="close">X</span>
    </span>
    <input type="text" @keydown.enter="addTag">
  </div>
</template>
<script>
  export default {
    name: 'App',
    data() {
      return {
       tags:['deneme','deneme2']
      }
    },
    methods:{
      addTag(event){
        this.tags.push(event.target.value)
        event.target.value = ''
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