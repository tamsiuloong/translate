<template>
  <div id="app">
    <h1>翻译一下</h1>
    <h5>简单 / 简单 / 简单</h5>
    <translate-from v-on:translate="translate"></translate-from>
    <translate-result :translateResult="translateResult"></translate-result>
  </div>
</template>

<script>
import TranslateFrom from './components/TranslateForm'
import TranslateResult from './components/TranslateResult'
export default {
  name: 'App',
  data: function () {
    return {
      translateResult: ''
    }
  },
  components: {TranslateFrom, TranslateResult},
  methods: {
    translate: function (text, language) {
      console.log(text + language)
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?' +
       'key=trnsl.1.1.20180125T051936Z.deb531945a21a170.a661b4e556481047819f26e97bf6aa62c0395800' +
       '&text=' + text + '&lang=' + language).then(function (resp) {
        this.translateResult = resp.data.text[0]
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
