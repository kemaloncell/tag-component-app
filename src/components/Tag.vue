<template>
  <span class="tag" :class="selectedColor">
      <span class="tag-content">{{tag}}</span>
      <span class="close" @click="$emit('remove-one-tag', index)">X</span>
    </span>
</template>
<script>
export default {
  props: {
    tag: {
      type: String,
      required: true
    },
    index: {
      type: Number,
      required: true
    },
    tagColor: {
      type: String,
      required: false
    }
  },
  data(){
    return{
      selectedColor: null
    }
  },
  created() {
    this.selectedColor = this.tagColor
  }
}
</script>


<style scoped>

.primary{
  background-color: #cce5ff;
  color: #004085;
  border-color:#b8daff;
}
.secondary{
  background-color: #e2e8e5;
  color: #868e96;
  border-color:#dee2e6;
}
.info{
  background-color: #cce5ff;
  color: #004085;
  border-color:#b8daff;
}
.warning{
  background-color: #ffe3b3;
  color: #004085;
  border-color:#b8daff;
}
.danger{
  background-color: #ffcbcb;
  color: #004085;
  border-color:#b8daff;
}
.success{
  background-color: #b3ffcc;
  color: #004085;
  border-color:#b8daff;
}

.tag *{
  font-size: 14px;
}
.tag{
  padding: 10px;
  cursor: default;
  margin-right: 10px;
}
.tag .close{
  font-size: 12px;
  font-weight: bold;
  cursor: pointer;
}
</style>