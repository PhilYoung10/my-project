<template>
  <div class="login">
    <div class="loginForm">
      <label for="userName">用户名:</label>
      <input v-model="user.userName" id="userName" placeholder="用户名">
      <br/>
      <label for="password">密&emsp;码:</label>
      <input v-model="user.password" type="password" id="password" placeholder="密码" v-on:keyup.enter="login">
      <br/>
      <button v-on:click="login">登录</button>
      <p>{{user.status}}</p>
    </div>
  </div>
</template>

<script>
  import Global from'/src/global'
  export default {
    name: 'login',
    data() {
      return {
        user:{
          userName:"Phil_Yang",
          password:"password",
          status:"未登录"
        }
      }
    },
    methods: {
      login:function () {
        this.user.status="Loding...  ";
        Global.loginStatus = 1;
      }
    }
  }
</script>

<style>
.loginForm {
  position: relative;
  width: 300px;
  left: calc(50% - 150px);
  margin-top: 20px ;
  padding: 20px 0 20px 0;
  border: solid #371250;
  border-radius: 5px;
}
</style>
