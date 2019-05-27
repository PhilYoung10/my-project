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
          <!--          <img src="static/icon/wulumuqishigongandashujuguanlipingtai-ico-.png">-->
          <Button v-on:click="logout" type="error" size="small">退出登录</Button>
        </div>
        <div class="functionMenu">
          <Divider>功能菜单</Divider>
          <div id="addProperty" class="function" v-on:click="addProperty">
            <img src="/static/icon/plus_128px_1160196_easyicon.net.png">
            <p>增加设备</p>
          </div>
          <div id="queryProperty" class="function" v-on:click="queryProperty">
            <img src="/static/icon/search_127.65957446809px_1138927_easyicon.net.png">
            <p>查询设备</p>
          </div>
          <div id="cabinetLayout" class="function" v-on:click="cabinetLayout">
            <img src="/static/icon/software_layout_header_columns_128.48301886792px_1183030_easyicon.net.png">
            <p>机柜布局图</p>
          </div>
        </div>
      </div>
      <div v-else>
        <div class="login">
          <Divider>Please Signin</Divider>

          <Form ref="formInline" :model="formInline" :rules="ruleInline" inline>
            <FormItem prop="user">
              <Input type="text" v-model="formInline.user" placeholder="Username">
              <Icon type="ios-person-outline" slot="prepend"></Icon>
              </Input>
            </FormItem>
            <FormItem prop="password">
              <Input type="password" v-model="formInline.password" placeholder="Password">
              <Icon type="ios-lock-outline" slot="prepend"></Icon>
              </Input>
            </FormItem>
            <br/>
            <FormItem>
              <Button type="primary" @click="handleSubmit('formInline')">Signin</Button>
            </FormItem>
          </Form>

          <!--          <div class="loginForm">-->
          <!--            <Input v-model="user.userName" id="userName" placeholder="用户名">-->
          <!--            <span slot="prepend">用户名:</span>-->
          <!--            <span slot="append">@aviva-cofco.com.cn</span>-->
          <!--            </Input>-->
          <!--            <Input type="password" v-model="user.password" id="password" placeholder="密码" v-on:keyup.enter="login" style="margin-top: 10px"/>-->
          <!--            <Button v-on:click="login" type="primary" size="small" style="margin-top: 10px">登录</Button>-->
          <!--          </div>-->
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
        isLogin: Global.loginStatus,
        checkUser: Global.checkUser(),

        formInline: {
          user: 'Phil_Yang',
          password: 'password',
          status: "0"
        },
        ruleInline: {
          user: [
            {required: true, message: 'Please fill in the user name', trigger: 'blur'}
          ],
          password: [
            {required: true, message: 'Please fill in the password.', trigger: 'blur'},
            {type: 'string', min: 6, message: 'The password length cannot be less than 6 bits', trigger: 'blur'}
          ]
        }
      }
    },
    components: {},
    methods: {
      handleSubmit(name) {
        this.$refs[name].validate((valid) => {
          if (valid) {
            this.$Message.success('Success!');
            this.formInline.status = "1";
            Global.loginStatus = 1;
            this.isLogin = 1;
          } else {
            this.$Message.error('User name or password is illegal!');
          }
        })
      },

      // login: function () {
      //   this.user.status = "1";
      //   Global.loginStatus = 1;
      //   this.isLogin = 1;
      // },
      logout: function () {
        this.user.status = "0";
        Global.loginStatus = 0;
        this.isLogin = 0;
        this.$Message.error('Logout!');
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
    /*padding: 20px;*/
    /*border: solid #371250;*/
    /*border-radius: 5px;*/
  }
</style>
