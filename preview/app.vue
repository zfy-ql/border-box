

<template>
  <div class="page">
    <div class="block component">
      <div class="title">组件</div>
      <div class="app">
        <div class="node">
          <com v-bind="componentProps"></com>
        </div>
      </div>
    </div>
    <div class="block editor">
      <div class="title">编辑面板</div>
      <div class="node">
        <editor :component-info="componentProps"></editor>
      </div>
    </div>
    <toast ref='toast' :compromise="true"></toast>
    <loading ref="loading"></loading>
    <img-viewer ref="imgViewer"></img-viewer>
  </div>
</template>

<script>
import com from '../src/index'
import Loading from './components/Loading'
import example from '../src/example'
import Editor from '../editor/index'
import ImgViewer from './components/ImgViewer'
import Toast from './components/Toast'
import MessageBox from 'mint-ui/message-box/'
import 'mint-ui/message-box/style.css'

export default {
  components: {Toast, Loading, ImgViewer, example, com, Editor},
  name: 'p',
  created () {
    var that = this
    window.msgBox = MessageBox
    window.alert = function (msg, fn) {
      MessageBox.close()
      var m, t
      if (typeof msg === 'object') {
        m = msg.msg
        t = msg.title
      } else {
        m = String(msg)
        t = '提示'
      }
      MessageBox.alert(m, t).then(action => {
        typeof fn === 'function' && fn(action)
      })
    }
    window.confirm = function (msg, fn, re) {
      MessageBox.close()
      var m, t
      if (typeof msg === 'object') {
        m = msg.msg
        t = msg.title
      } else {
        m = String(msg)
        t = '提示'
      }
      MessageBox.confirm(m, t).then(action => {
        typeof fn === 'function' && fn(action)
      }).catch(action => {
        typeof re === 'function' && re(action)
      })
    }
    window.prompt = function (msg, fn, re) {
      MessageBox.close()
      var m, t
      if (typeof msg === 'object') {
        m = msg.msg
        t = msg.title
      } else {
        m = String(msg)
        t = '提示'
      }
      MessageBox.prompt(m, t).then(val => {
        typeof fn === 'function' && fn(val)
      }).catch(action => {
        typeof re === 'function' && re(action)
      })
    }
    window.loading = function (hide) {
      if (!that.$refs['loading']) return
      if (!hide) that.$refs['loading'].open()
      else that.$refs['loading'].hide()
    }
    window.toast = function (msg, fn) {
      if (!that.$refs['toast']) return
      that.$refs['toast'].render({msg, fn})
    }
    window.viewImg = (imgs, index) => {
      if (!that.$refs.imgViewer) return
      that.$refs.imgViewer.open(imgs, index)
    }
  },
  data () {
    return {
      componentProps: {
        type: 'Border1',
        reverse: false,
        dur: 3,
        title: '标题',
        titleWidth: 250,
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
          },
        },
      },
    }
  },
  methods: {
    getComponent (order) {
      return this.$refs.ones[order - 1]
    }
  }
}
</script>

<style lang="stylus" rel="stylesheet/stylus" type="text/stylus">
@require './style.css';

html, body {
  margin: 0;
  padding: 0;
}

.product {
  height: 200px;
  border: solid 1px #ccc
}

.app {
  height: 560px;
  box-shadow: 1px 1px 1px 1px #ccc
  overflow auto
  &::-webkit-scrollbar {
    display: none;
  }
}

.page {
  display: flex;
  flex-direction: row;
  width: 100%;

  .block {
    margin: 10px;
    min-height: 200px;
    margin-bottom: 20px;
    box-shadow: 0px 5px 10px 0px #ccc;
    background-color: #fff;

    &.component {
      width: 720px;
      .node {
        width 300px
        height 200px
      }
    }
    &.editor {
      flex: 1;

      .node {
        padding: 20px;
      }
    }

    .title {
      border-bottom: 1px solid #ccc;
      box-shadow: 0px -1px 10px 0px #ccc;
      color: #666;
      padding: 10px;
    }
  }
}

</style>


