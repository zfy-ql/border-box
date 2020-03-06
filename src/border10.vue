<template>
  <dv-border-box-10 :color="[comStyle.color1 || 'rgb(29, 72, 196)', comStyle.color2 || 'rgb(211, 225, 248)']">dv-border-box-10</dv-border-box-10>
</template>

<script>
  // import StepIndicator from 'vue-step-indicator'
  import Vue from 'vue'
  import { borderBox10 } from '@jiaminghi/data-view'

  Vue.use(borderBox10)

  export default {
    name: 'Border10',
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
