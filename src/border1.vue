<template>
  <dv-border-box-1 :color="[comStyle.color1, comStyle.color2]">dv-border-box-1</dv-border-box-1>
</template>

<script>
  // import StepIndicator from 'vue-step-indicator'
  import Vue from 'vue'
  import { borderBox1 } from '@jiaminghi/data-view'

  Vue.use(borderBox1)

  export default {
    name: 'Border2',
    data () {
      return {
      }
    },
    props: {
      comStyle: {
        type: Object,
        default: {}
      }
    },
    watch: {

    },
    components: {
      // StepIndicator
    },
    computed: {
    },
    mounted: function () {
    },
    methods: {

    }
  }
</script>
<style>
  .el-step__title {
    font-size: 12px !important;
    line-height: 30px;
  }
  .el-step__icon {
    width: 20px;
    height: 20px;
    font-size: 12px;
  }
  .el-step__icon.is-text {
    border-width: 1px;
  }
</style>

<style lang="stylus" rel="stylesheet/stylus" type="text/stylus" scoped>
  // @import './step-indictor.css';

  .step1Wrap {
    // width: 50%;

    .el-step__title {
      font-size: 12px;
    }
  }
</style>
