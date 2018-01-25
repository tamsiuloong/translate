<template>
  <form class="form-inline">
    <div class="form-group">
      <input class="form-control" type="text" v-model="text" placeholder="请输入需要翻译的内容"/>
    </div>
    <div class="form-group">
      <!-- https://tech.yandex.com/translate/doc/dg/concepts/api-overview-docpage/ -->
      <select v-model="language" class="form-control">
        <option value="en">英文</option>
        <option value="zh">Chinese</option>
        <option value="ru">Russian</option>
        <option value="ko">Korean</option>
      </select>
    </div>
    <div class="form-group">
      <input class="btn btn-danger" type="submit" @click="translate" value="翻译"/>
    </div>
  </form>
</template>

<script>
export default {
  name: 'translateForm',
  data () {
    return {
      text: '',
      language: 'en'
    }
  },
  methods: {
    translate: function (e) {
      // 触发父组件的 translate 事件
      this.$emit('translate', this.text, this.language)
      // 取消默认的form提交事件
      e.preventDefault()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
