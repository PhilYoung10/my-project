<template>
  <div id="app">
    <img src="./assets/logo.png">
    <helloVue></helloVue>
<!--    <router-view/>-->
    <dataRelate></dataRelate>
  </div>
</template>

<script>
  // 导入组件

  import HelloVue from './components/HelloVue'
  import DataRelate from './components/DataRelate'
  export default {
    name: 'app',
    components: {
      HelloVue,
      DataRelate
    }
  }


// export default {
//   name: 'App'
// }
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
