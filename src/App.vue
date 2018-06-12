<template>
  <div id="app">
    <div class="container">
      <h1>在线翻译</h1>
      <h5 class="text-muted">简单    /    易用    /    便捷</h5>
      <translateForm v-on:formSubmit="translateText"></translateForm>
      <translateOutput v-text="translatedText"></translateOutput>
    </div>
  </div>
</template>

<script>

import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'

export default {
  name: 'app',
  data: function() {
    return{
      translatedText: ""
    }
  },
  components: {
    TranslateForm,TranslateOutput
  },
  methods: {
    translateText:function(text,language) {
      // alert(text);
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180611T144321Z.754b5653fdd7169e.91b0f7a9b39a5010390f11dfea2ce4bf9f0bf449&lang='+language+'&text='+text)
          .then((response)=>{
            this.translatedText = response.body.text[0];
          })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;


}
</style>
