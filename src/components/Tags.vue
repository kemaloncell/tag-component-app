<template>
  <div class="tag-container">
    <Tag
        v-for="(tag, index) in tags"
        :tag="tag"
        :index="index"
        @remove-one-tag="removeOneTag"
    />
      <input
          type="text"
          @keydown.enter="addTag"
          @keydown.backspace="removeTag"
      >
      <div v-if="error" class="error">Bu etiket daha önceden eklenmiş!!</div>
  </div>
</template>
<script>
import Tag from './Tag.vue'
export default {
  components: {
    Tag
  },
  props: {
    value: {
      type: String,
      required: false
    }
  },
  data() {
    return {
      tags:['denem2e','deneme2'],
      error:false,
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
  },
  watch:{
    tags(){
      this.$emit('input', this.tags.join(','))
    }
  },
  created() {
    if(this.value){
     if(this.value.length > 0){
       this.tags = this.value.split(',')
     }
    }
  }
}
</script>

<style scoped>
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
</style>