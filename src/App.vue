<template>
  <div class="tag-container">
    <span class="tag">
      <span class="tag-content">Vue</span>
      <span class="close">X</span>
    </span>
  </div>
</template>
<script>
  export default {
    name: 'App',
    data() {
      return {
        message: 'Hello Vue!'
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
  padding: 2rem;
}

.tag{
  background-color: #fbbd08;
  padding: 1rem;
  color: #000;
  cursor: default;
  font-size:14px
}

.tag .close{
  font-size: 12px;
  cursor: pointer;
}

</style>