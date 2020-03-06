<template>
  <dv-border-box-8 :dur="dur" :color="[comStyle.color1 || 'rgb(35, 95, 167)', comStyle.color2 || '#53cbd9']">dv-border-box-8</dv-border-box-8>
</template>

<script>
  // import StepIndicator from 'vue-step-indicator'
  import Vue from 'vue'
  import { borderBox8 } from '@jiaminghi/data-view'

  Vue.use(borderBox8)

  export default {
    name: 'Border8',
    data () {
      return {
      }
    },
    props: {
      dur: {
        type: Number,
        default: 3
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
