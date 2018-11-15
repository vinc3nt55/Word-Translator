<template>
  <div class="output-container">
    <h2 class="output text-success">{{ translatedText }}</h2>
  </div>
</template>
<script>
export default {
  name: 'translateOutput',
  props: ['translatedText'],
}
</script>

<style>
.output-container{
  width: 100%;
  margin: 0 auto;
  margin-top: 25px;
  font-size: 2rem; 
  background-color: #fff;
}
.output{
  width: 100%;
}
</style>
