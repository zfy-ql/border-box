<template>
  <dv-border-box-13 :color="[comStyle.color1 || 'rgb(46, 96, 153)', comStyle.color2 || 'rgb(124, 231, 253)']">dv-border-box-13</dv-border-box-13>
</template>

<script>
  // import StepIndicator from 'vue-step-indicator'
  import Vue from 'vue'
  import { borderBox13 } from '@jiaminghi/data-view'

  Vue.use(borderBox13)

  export default {
    name: 'Border13',
    data () {
      return {
      }
    },
    props: {
      comStyle: {
        type: Object,
        default: {
        }
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
