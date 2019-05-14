<template>
  <!--  <div id="app">-->
  <!--    <img src="./assets/logo.png">-->
  <!--    <helloVue></helloVue>-->
  <!--&lt;!&ndash;    <router-view/>&ndash;&gt;-->
  <!--    <dataRelate></dataRelate>-->
  <!--  </div>-->

  <div id="app" class="container">
    <div class="head">
      <img id="companyLogo" src="/static/icon/Logo%20(1).png">
      <p class="systemName">资产管理系统</p>
    </div>
    <div class="main">
      <div v-if="isLogin" class="functionMenu">
        <div id="addProperty" class="function">
          <img src="/static/icon/plus_128px_1160196_easyicon.net.png">
          <p>增加设备</p>
        </div>
        <div id="queryProperty" class="function">
          <img src="/static/icon/search_127.65957446809px_1138927_easyicon.net.png">
          <p>查询设备</p>
        </div>
        <div id="cabinetLayout" class=  "function">
          <img src="/static/icon/software_layout_header_columns_128.48301886792px_1183030_easyicon.net.png">
          <p>机柜布局图</p>
        </div>
      </div>
      <div v-else>
        <login></login>
      </div>
    </div>
  </div>
</template>

<script>
  // 导入组件
  // import HelloVue from './components/HelloVue'
  // import DataRelate from './components/DataRelate'
  // export default {
  //   name: 'app',
  //   components: {
  //     HelloVue,
  //     DataRelate
  //   }
  // }

  import Login from'./components/Login'
  export default {
    name: 'app',
    data() {
      return {
        isLogin: Login.loginStatus()
      }
    },
    components:{
      Login
    }
  }
</script>

<style>

  /*#app {*/
  /*  font-family: 'Avenir', Helvetica, Arial, sans-serif;*/
  /*  -webkit-font-smoothing: antialiased;*/
  /*  -moz-osx-font-smoothing: grayscale;*/
  /*  text-align: center;*/
  /*  color: #2c3e50;*/
  /*  margin-top: 60px;*/
  /*}*/
  .container {
    text-align: center;
  }

  img {
    width: auto;
    height: auto;
    max-width: 100%;
    max-height: 100%;
  }

  .head {
    width: 100%;
  }

  #companyLogo {
    width: 400px;
    margin-top: 30px;
  }

  .systemName {
    color: #371250;
    font-size: 40px;
  }

  .function {
    display: inline-block;
    padding: 20px;
  }
</style>
