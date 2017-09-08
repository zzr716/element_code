<template>
  <div id="app">
    <el-button :loading="true" @click="doDefaultTap" size="large">默认按钮</el-button>
    <el-button type="primary" :disabled="true">主要按钮</el-button>
    <el-button icon="edit" type="text">文字按钮</el-button>
    <div>
      <el-button-group>
        <el-button icon="arrow-left" type="primary">上一页</el-button>
        <el-button type="primary">下一页<i class="el-icon-arrow-right el-icon--right"></i></el-button>
      </el-button-group>
      <el-button-group>
        <el-button type="primary" icon="edit"></el-button>
        <el-button type="primary" icon="share"></el-button>
        <el-button type="primary" icon="delete"></el-button>
      </el-button-group>
    </div>
    <div>
      <el-button type="text" @click="dialogVisible=true">点击打开Dialog</el-button>
      <el-dialog  title="提示" :visible.sync="dialogVisible">
        <span>这是一段信息</span>
        <span slot="footer" class="dialog-footer">
          <el-button @click="dialogVisible=false">取消</el-button>
          <el-button type="primary" @click="dialogVisible=false">确定</el-button>
        </span>
      </el-dialog>
    </div>
    <div>
      <span class="demonstration">默认Hover指示器触发</span>
      <el-carousel :interval="1000" :initialIndex="2" height="150px">
        <el-carousel-item v-for="item in 4" :key="item">
          <h3>{{item}}</h3>
        </el-carousel-item>
      </el-carousel>
    </div>
    <router-view></router-view>
  </div>
</template>

<script>
import ElCarousel from './components/ElCarousel/ElCarousel'
import ElCarouselItem from './components/ElCarouselItem/ElCarouselItem'
import ElDialog from './components/ElDialog/ElDialog'
import ElButton from './components/ElButton/ElButton'
import ElButtonGroup from './components/ElButtonGroup/ElButtonGroup'
export default {
  name: 'app',
  data () {
    return {
      dialogVisible: false
    }
  },
  methods: {
    doDefaultTap (evt) {
      console.log('tapped')
      console.log(evt)
    }
  },
  components: {
    "el-button": ElButton,
    "el-button-group": ElButtonGroup,
    "el-dialog": ElDialog,
    "el-carousel": ElCarousel,
    "el-carousel-item": ElCarouselItem
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
