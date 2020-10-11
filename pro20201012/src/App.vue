<template>
  <div id="app">
    <el-container class="layout-default">
        <el-header height="">
          <my-header />
        </el-header>
        <el-main>
        </el-main>
        <el-footer height="">
          <my-footer />
        </el-footer>
    </el-container>
  </div>
</template>

<script>
import myHeader from './components/myHeader';
import myFooter from './components/myFooter';

export default {
  name: 'App',
  components: {
    myHeader,
    myFooter
  }
}
</script>

<style>
/* #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
