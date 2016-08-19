<template>
  <div id="app">
    <form>
      <div class="form-group">
        <num-picker :count.sync="count" :max="10"></num-picker>
      </div>
    </form>

  </div>
</template>

<script>
  import NumPicker from './components/num-picker/num-picker.vue'

  export default {
    components: {
      'num-picker': NumPicker
    },
    data () {
      return {
      }
    }
  }
</script>

<style lang="less">
  * {
    margin: 0;
    padding: 0;
  }
  #app {
    margin: 100px;
    width: 300px;
  }
</style>
