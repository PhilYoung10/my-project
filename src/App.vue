<template>

  <div id="app" class="container">
    <div class="head">
      <img id="companyLogo" src="/static/icon/Logo%20(1).png">
      <p class="systemName">资产管理系统</p>
    </div>
    <div class="main">
      <div v-if="isLogin">
        <div class="logout">
          <p style="display: inline-block">{{user.userName}}</p>
          <button v-on:click="logout">退出登录</button>
        </div>
        <div class="functionMenu">
          <div id="addProperty" class="function"  v-on:click="addProperty">
            <img src="/static/icon/plus_128px_1160196_easyicon.net.png">
            <p>增加设备</p>
          </div>
          <div id="queryProperty" class="function"  v-on:click="queryProperty">
            <img src="/static/icon/search_127.65957446809px_1138927_easyicon.net.png">
            <p>查询设备</p>
          </div>
          <div id="cabinetLayout" class="function"  v-on:click="cabinetLayout">
            <img src="/static/icon/software_layout_header_columns_128.48301886792px_1183030_easyicon.net.png">
            <p>机柜布局图</p>
          </div>
        </div>
      </div>
      <div v-else>
        <div class="login">
          <div class="loginForm">
            <label for="userName">用户名:</label>
            <input v-model="user.userName" id="userName" placeholder="用户名">
            <br/>
            <label for="password">密&emsp;码:</label>
            <input v-model="user.password" type="password" id="password" placeholder="密码" v-on:keyup.enter="login">
            <br/>
            <button v-on:click="login">登录</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Global from './global'

  export default {
    name: 'app',
    data() {
      return {
        user: {
          userName: "Phil_Yang",
          password: "password",
          status: "0"
        },
        isLogin: Global.loginStatus
      }
    },
    components: {},
    methods: {
      login: function () {
        this.user.status = "1";
        Global.loginStatus = 1;
        this.isLogin = 1;
      },
      logout:function () {
        this.user.status = "0";
        Global.loginStatus = 0;
        this.isLogin = 0;
      },
      addProperty: function () {

      },
      queryProperty: function () {
        
      },
      cabinetLayout: function () {

      }
    }
  }
</script>

<style>
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

  .systemName {
    color: #371250;
    font-size: 40px;
  }

  #companyLogo {
    width: 400px;
    margin-top: 30px;
  }

  .function {
    display: inline-block;
    padding: 20px;
  }

  .loginForm {
    position: relative;
    width: 300px;
    left: calc(50% - 150px);
    margin-top: 20px;
    padding: 20px 0 20px 0;
    border: solid #371250;
    border-radius: 5px;
  }
</style>
