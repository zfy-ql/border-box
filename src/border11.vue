<template>
  <dv-border-box-11 :titleWidth="titleWidth" :title="title" :color="[comStyle.color1 || '#8cacf9', comStyle.color2 || '#24316b']">dv-border-box-11</dv-border-box-11>
</template>

<script>
  // import StepIndicator from 'vue-step-indicator'
  import Vue from 'vue'
  import { borderBox11 } from '@jiaminghi/data-view'

  Vue.use(borderBox11)

  export default {
    name: 'Border11',
    data () {
      return {
      }
    },
    props: {
      title: {
        type: String,
        default: '标题'
      },
      titleWidth: {
        type: Number,
        default: 250
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
