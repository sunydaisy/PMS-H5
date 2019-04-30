<template>
  <div class="login-box">
    <div class="login-logo">
      <img src="../assets/lc-logo.png">
    </div>
    <div class="login-form">
      <div class="form-title">
        <p class="font-logo">PMS</p>
        <P class="logo-desc">项目信息管理系统</P>
      </div>
      <div class="login-error-box">
        <span v-show="errorUserMsg !== ''">{{errorUserMsg}}</span>
      </div>
      <div class="form">
        <div class="inp-wrap">
          <span>用户名</span>
          <input type="text" placeholder="请输入用户名" autocomplete="off" @focus="clearErrMsg">
        </div>
        <div class="login-error">
          <span v-show="errorUserName !== ''">{{errorUserName}}</span>
        </div>
        <div class="inp-wrap">
          <span>密码</span>
          <input type="text" placeholder="请输入密码" autocomplete="off" @focus="clearErrMsg">
        </div>
        <div class="login-error">
          <span v-show="errorPassWord !== ''">{{errorPassWord}}</span>
        </div>
        <div class="inp-wrap">
          <span></span>
          <input type="button" class="login-btn" @click="login" value="登录">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'login',
  data() {
    return {
      loginForm: {
        userName: '',
        passWord: ''
      },
      errorUserMsg: '',
      errorUserName: '',
      errorPassWord: ''
    }
  },
  methods: {
    clearErrMsg() {
      this.errorUserMsg = ''
      this.errorUserName = ''
      this.errorPassWord = ''
    },
    login() {
      if (this.loginForm.userName === '') {
        this.errorUserName = '请输入用户名'
        return false
      }
      if (this.loginForm.passWord === '') {
        this.errorPassWord = '请输入密码'
        return false
      }
    }
  }
}
</script>

<style lang="scss">
.login-box {
  background: url('../assets/login-bg.png') no-repeat center center;
  background-size: cover;
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  .login-logo {
    width: 200px;
    height: 100px;
    text-align: center;
    position: absolute;
    top: 20px;
    left: 30px;
  }
  .login-form {
    width: 580px;
    background-color: rgba(255, 255, 255, 0.25);
    border-radius: 8px;
    padding: 25px 0;
    .form-title {
      height: 75px;
      .font-logo {
        color: #ff9e00;
        font-size: 48px;
        text-align: center;
        font-style: oblique;
        font-weight: 600;
        font-family: Arial, Helvetica, sans-serif;
        line-height: 1;
      }
      .logo-desc {
        color: #ff9800;
        font-size: 16px;
        text-align: center;
        font-family: Arial, Helvetica, sans-serif;
        line-height: 1.5;
      }
    }
    .login-error-box {
      height: 20px;
      color: #ed6347;
      text-align: center;
    }
    .form {
      width: 394px;
      margin: 0px 73px 20px 83px;
      .login-error {
        height: 20px;
        color: #ed6347;
        text-align: left;
        padding-left: 84px;
      }
      .inp-wrap {
        height: 58px;
        padding-top: 10px;
        span {
          width: 84px;
          display: block;
          text-align: right;
          float: left;
          padding: 10px 20px 10px 10px;
          font-size: 16px;
        }
        input {
          width: 300px;
          height: 46px;
          padding: 0 10px;
          background-color: rgba(255, 255, 255, 0.61);
          border: solid 1px #bbbbbb9e;
        }
        .login-btn {
          font-size: 18px;
          color: #858585;
        }
      }
    }
  }
}
</style>
