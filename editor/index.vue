<template>
  <div class="component-editor">
    <el-card class="box-card" header='设置'>
      <el-collapse accordion value="1">
        <el-collapse-item title="基础设置" name="1">
          <el-form size="mini">
            <el-form-item label="边框颜色--主颜色">
              <el-input type="color" v-model="componentInfo.comStyle.color1" placeholder="请输入颜色"></el-input>
            </el-form-item>
            <el-form-item label="边框颜色--副颜色">
              <el-input type="color" v-model="componentInfo.comStyle.color2" placeholder="请输入颜色"></el-input>
            </el-form-item>
          </el-form>
        </el-collapse-item>
        <el-collapse-item title="参数设置" name="1">
          <el-form size="mini">
            <el-form-item label="选择类型">
              <el-select v-model="componentInfo.type" placeholder="请选择">
                <el-option v-for="item in defaultType" :key="item.value" :label="item.label" :value="item.value">
                </el-option>
              </el-select>
            </el-form-item>
            <el-form-item label="是否翻转" v-if="componentInfo.type == 'Border4' || componentInfo.type == 'Border5'">
              <el-select v-model="componentInfo.reverse" placeholder="请选择">
                <el-option label="否" :value="false">
                </el-option>
                <el-option label="是" :value="true">
                </el-option>
              </el-select>
            </el-form-item>
            <el-form-item label='单次动画时长(秒)' v-if="componentInfo.type=='Border8'">
              <el-input type='number' v-model.number="componentInfo.dur" placeholder="请输入单次动画时长"></el-input>
            </el-form-item>
            <el-form-item label="标题" v-if="componentInfo.type=='Border11'">
              <el-input type="input" v-model="componentInfo.title" placeholder="请输入标题"></el-input>
            </el-form-item>
            <el-form-item label='标题宽度' v-if="componentInfo.type=='Border11'">
              <el-input type='number' v-model.number="componentInfo.titleWidth" placeholder="请输入标题宽度"></el-input>
            </el-form-item>
          </el-form>
        </el-collapse-item>
      </el-collapse>
    </el-card>
  </div>
</template>

<script>
  export default {
    name: 'maliangeditor',
    props: {
      componentInfo: { // 固定字段，收集所有属性值
        type: '',
        reverse: false,
        dur: 3,
        default: {
          comStyle: {
            color1: 'rgb(35, 95, 167)',
              color2: 'rgb(79, 210, 221)'
          }
        }
      }
    },
    data: function () {
      return {
        defaultType: [{
          label: '边框1',
          value: 'Border1'
        }, {
          label: '边框2',
          value: 'Border2'
        }, {
          label: '边框3',
          value: 'Border3'
        }, {
          label: '边框4',
          value: 'Border4'
        }, {
          label: '边框5',
          value: 'Border5'
        }, {
          label: '边框6',
          value: 'Border6'
        }, {
          label: '边框7',
          value: 'Border7'
        }, {
          label: '边框8',
          value: 'Border8'
        }, {
          label: '边框9',
          value: 'Border9'
        }, {
          label: '边框10',
          value: 'Border10'
        }, {
          label: '边框11',
          value: 'Border11'
        }, {
          label: '边框12',
          value: 'Border12'
        }, {
          label: '边框13',
          value: 'Border13'
        }]
      }
    },
    computed: {
    },
    watch: {
      componentInfo: {
        hanlder: function (v) {
          console.log('editor index', v)
        },
      }
    },
    mounted: function () {
    },
    methods: {
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus" type="text/stylus" scoped>
  .component-editor {
  }
</style>
