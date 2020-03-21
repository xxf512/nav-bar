<!--
 * @Author: your name
 * @Date: 2020-03-21 15:27:45
 * @LastEditTime: 2020-03-21 17:53:48
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: \hello-world\src\components\HelloWorld.vue
 -->
<template>
  <div class="hello">
    <div :class="leftStyle">
      <el-card class="box-card">
        左边内容
      </el-card>
      <!-- 导航栏 -->
      <div :class="navStyle">
        <div :class="iconStyle" @click="state = !state">
          <i :class="icon"></i>
        </div>
        <ul class="nav-bar">
          <li class="nav-bar-item">
            <div class="item-title">
              <i class="el-icon-menu"></i>
            </div>
            <div class="item-title">
              <i class="el-icon-menu"></i>
            </div>
          </li>
        </ul>
      </div>
    </div>
    <div :class="rightStyle" class="transition" v-show="state">
      <el-card class="box-card">
        右边内容
      </el-card>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  computed: {
    leftStyle () {
      return !this.state ? 'left-expand' : 'left'
    },
    rightStyle () {
      return !this.state ? 'right-expand' : 'right'
    },
    navStyle () {
      return this.state ? 'nav nav-expand' : 'nav nav-not-expand'
    },
    iconStyle () {
      return this.state ? 'icon' : 'icon-not-expand'
    },
    icon () {
      return this.state ? 'el-icon-d-arrow-right' : 'el-icon-d-arrow-left'
    }
  },
  data () {
    return {
      state: true
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
.hello {
  height: 800px;
  display: flex;
  flex-direction: row;
  // overflow: hidden;
  .box-card {
    height: 100%;
  }
  .transition{
    transition: all .3s ease-out;
  }
  .left {
    margin-right: 60px;
    position: relative;
    flex: 0.4;
    transition: all .3s ease-out;
  }
  .nav {
    width: 50px;
    height: 100%;
    background-color: #012154;
    .nav-bar {
      height: 100%;
      list-style: none;
      position: relative;
      margin: 0;
      padding-left: 0;
      .nav-bar-item {
        height: 50px;
        line-height: 50px;
        font-size: 14px;
        color: #ffffff;
        padding: 0 20px;
        list-style: none;
        cursor: pointer;
        position: relative;
        transition: border-color .3s,background-color .3s,color .3s;
        box-sizing: border-box;
        white-space: nowrap;
        .item-title {

        }
      }
    }
    .icon {
      position: absolute;
      margin-left: -40px;
      width: 40px;
      height: 40px;
      font-size: 14px;
      cursor: pointer;
      color: #ffffff;
      text-align: center;
      line-height: 40px;
      background-color: #525152;
      opacity: .833;
    }
    .icon-not-expand {
      position: absolute;
      margin-right: -40px;
      right: 0;
      width: 40px;
      height: 40px;
      font-size: 14px;
      cursor: pointer;
      color: #ffffff;
      text-align: center;
      line-height: 40px;
      background-color: #525152;
      opacity: .833;
    }
  }
  .nav-expand {
    position: absolute;
    margin-right: -60px;
    top: 0;
    right: 0;
  }
  .nav-not-expand {
    position: absolute;
    margin-right: -50px;
    top: 0;
    right: 0;
  }
  .left-expand {
    position: relative;
    flex: 1;
    transition: all .3s ease-out;
  }
  .right {
    position: relative;
    flex: 1;
  }
  .right-expand {
    position: relative;
    flex: 0;
  }
}
</style>
