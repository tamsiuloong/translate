<template>
  <div>
    <textarea class="form-control" rows="3">{{translateResult}}</textarea>

  </div>
</template>

<script>
export default {
  name: 'TranslateResult',
  props: ['translateResult'],
  data () {
    return {
      msg: '翻译结果'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
