<template>
  <div id="translateOutput">
    <h2>{{translatedText}}</h2>
  </div>
</template>

<script>


export default {
  name: 'translateOutput',
  props:[
    "translatedText"
  ]
}
</script>

<style>
  #translateOutput{
    margin-top: 20px;
    font-size: 40px;
  }
</style>
