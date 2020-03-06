<template>
  <dv-border-box-3 :color="[comStyle.color1 || 'rgb(40, 98, 183)', comStyle.color2 || 'rgb(40, 98, 183)']">dv-border-box-3</dv-border-box-3>
</template>

<script>
  // import StepIndicator from 'vue-step-indicator'
  import Vue from 'vue'
  import { borderBox3 } from '@jiaminghi/data-view'

  Vue.use(borderBox3)

  export default {
    name: 'Border3',
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
