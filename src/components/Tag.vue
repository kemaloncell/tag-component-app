<template>
  <span class="tag">
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
    }
  },
}
</script>


<style scoped>
.tag *{
  font-size: 14px;
}
.tag{
  background-color: #fbbd08;
  padding: 10px;
  color: #000;
  cursor: default;
  margin-right: 10px;
}
.tag .close{
  font-size: 12px;
  font-weight: bold;
  cursor: pointer;
}
</style>