<template>
  <div class="tag-container">
    <span class="tag" v-for="(tag, index) in tags">
      <span class="tag-content">{{tag}}</span>
      <span class="close" @click="removeOneTag(index)">X</span>
    </span>
    <input
        type="text"
        @keydown.enter="addTag"
        @keydown.backspace="removeTag"
    >
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
        let text = event.target
        if(text.value.length > 0){
          if(this.tags.includes(text.value.toLowerCase())){
            this.error = true
            setTimeout(() =>{
              this.error = false
            }, 2000);

          }else{
            this.tags.push(text.value)
            this.error = false
            text.value = ''
          }
        }
      },
      removeTag(event){
        let text = event.target
        if(text.value.length === 0){
          this.tags.splice(this.tags.length -1 ,1)
        }
      },
      removeOneTag(index){
        this.tags.splice(index,1)
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