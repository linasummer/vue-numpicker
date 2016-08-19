<template>
  <div class="num-picker">
    <button type="button" class="minus glyphicon-minus" :disabled="count <= min" @click="decrease"></button>
    <input type="number" name="count" title="请输入数量" class="num" v-model="count" @blur="putNumber">
    <button type="button" class="plus glyphicon-plus" :disabled="count >= max" @click="increase"></button>
  </div>
</template>

<script type="text/babel">
  export default {
    props: {
      count: { //数值
        default: 1
      },
      min: { //最小值
        type: Number,
        default: 1
      },
      max: { //最大值
        type: Number
      }
    },
    data() {
      return {}
    },
    ready() {

    },
    methods: {
      // 减
      decrease () {
        this.count--;
      },

      // 增
      increase () {
        this.count++;
      },

      // 输入大于最大值，填入最大值，输入小于最小值，填入最小值
      putNumber () {
        if (this.count < this.min) {
          this.count = this.min
        } else if (this.count > this.max) {
          this.count = this.max
        } else {
          return true
        }
      }
    }
  }
</script>

<style lang="less" rel="stylesheet/less">
.num-picker {

  button {
    width: 30px;
    height: 30px;
    border: none;
    &[disabled] {
      background-color: #eeeeee;
      opacity: 0.8;
    }
  }

  .num {
    width: 50px;
    height: 30px;
    text-align: center;

  }

  input::-webkit-outer-spin-button,
  input::-webkit-inner-spin-button {
    -webkit-appearance: none;
  }

  input[type="number"] {
    -moz-appearance: textfield;
  }

}
</style>
