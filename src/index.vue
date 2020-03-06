<template>
  <div class="component">
    <component v-if="type" :comStyle='comStyle' :reverse="reverse" :dur="dur" :title="title" :titleWidth="titleWidth" :is="type"></component>
  </div>
</template>

<script>
  import {VueExtend} from 'godspen-lib'
  import Border1 from './border1'
  import Border2 from './border2'
  import Border3 from './border3'
  import Border4 from './border4'
  import Border5 from './border5'
  import Border6 from './border6'
  import Border7 from './border7'
  import Border8 from './border8'
  import Border9 from './border9'
  import Border10 from './border10'
  import Border11 from './border11'
  import Border12 from './border12'
  import Border13 from './border13'

  export default {
    mixins: [VueExtend.mixin],
    name: 'border-box',
    label: process.env.LABEL,
    style: process.env.STYLE,
    components: { Border1, Border2, Border3, Border4, Border5, Border6, Border7, Border8, Border9, Border10, Border11, Border12, Border13 },
    props: {
      type: {
        type: [ String ],
        default: '选择border类型',
        editer: {
          ignore: true // 忽略，码良基础在编辑器中不显示
        }
      },
      reverse: {
        type: Boolean,
        default: '是否翻转',
        editer: {
          ignore: true // 忽略，码良基础在编辑器中不显示
        }
      },
      dur: {
        type: Number,
        default: 3,
        editer: {
          ignore: true // 忽略，码良基础在编辑器中不显示
        }
      },
      title: {
        type: String,
        default: '标题',
        editer: {
          ignore: true // 忽略，码良基础在编辑器中不显示
        }
      },
      titleWidth: {
        type: Number,
        default: 250,
        editer: {
          ignore: true // 忽略，码良基础在编辑器中不显示
        }
      },
      comStyle: {
        type: Object,
        default: function () {
          return {
            color1: 'rgb(35, 95, 167)',
            color2: 'rgb(79, 210, 221)'
          }
        },
        editer: {
          ignore: true // 忽略，码良基础在编辑器中不显示
        }
      }
    },
    data () {
      return {
      }
    },
    computed: {
    },
    editorMethods: {
    },
    methods: {
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus" type="text/stylus" scoped>
  .component {
    color: #46bd87;
    height 300px
    line-height 300px
    padding 20px
    text-align center
    background-color #000
  }
</style>
