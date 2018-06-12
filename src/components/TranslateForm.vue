<template>
  <div id="translateForm" class="">
    <div class="">
      <form class="form" v-on:submit="formSubmit">
        <input class="input1"  type="text" placeholder="输入需要翻译的内容" v-model="textToTranslate">
        <select v-model="language">
          <option value="en">English</option>
          <option value="ru">Russian</option>
          <option value="ko">Korean</option>
          <option value="ja">Japanese</option>
          <option value="zh">Chinese</option>
        </select>
        <input class="input2" type="submit" name="" value="翻译">
      </form>
    </div>

  </div>
</template>

<script>


export default {
  name: 'translateForm',
  data: function(){
    return {
      textToTranslate: "",
      language: ""
    }
  },
  methods: {
    formSubmit:function(e) {
      // alert("hello")
      // alert(this.textToTranslate);
      this.$emit("formSubmit",this.textToTranslate,this.language);
      e.preventDefault();  //取消默认事件
    }
  },
  created:function(){
    this.language = "en";
  }
}
</script>

<style>
  .form select{
    border-radius: 4px;
    height: 24px;
  }
  .input1{
    height: 20px;
    font-size: 18px;
    line-height: 20px;
    border-radius: 8px;
  }
  .input2{
    height: 26px;
    line-height: 20px;
    width: 50px;
    border-radius: 12px;
  }
</style>
