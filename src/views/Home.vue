<!--
 * @Author: your name
 * @Date: 2020-03-21 15:27:45
 * @LastEditTime: 2020-03-21 15:43:03
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: \hello-world\src\views\Home.vue
 -->
<template>
  <div class="home">
    <HelloWorld/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  }
}
</script>
<style lang="less" scoped>
.home {
  padding: 20px;
  width: 1400px;
  margin: 0 auto;
}
</style>
