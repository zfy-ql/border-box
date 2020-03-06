<template>
  <dv-border-box-4 :reverse="reverse" :color="[comStyle.color1 || 'red', comStyle.color2 || 'rgba(0, 0, 255, 0.8)']">dv-border-box-4</dv-border-box-4>
</template>

<script>
  // import StepIndicator from 'vue-step-indicator'
  import Vue from 'vue'
  import { borderBox4 } from '@jiaminghi/data-view'

  Vue.use(borderBox4)

  export default {
    name: 'Border4',
    data () {
      return {
      }
    },
    props: {
      reverse: {
        type: Boolean,
        default: false
      },
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
