<template>
  <!--登录-->
  <div class="login">
    <!--登录头-->
    <div class="login-header">

      <div class="left"> <router-link to="/home"><i class="iconfont-fanhui icon-fanhui"></i></router-link></div>
      <div class="center"><span>登录</span></div>
      <div class="right"> <router-link to="/register">注册</router-link></div>
    </div>
    <!--登录输入框-->
    <div class="login-input">
      <div class="login-avatar">
        <div class="avatar"></div>
      </div>
      <div class="input-height">
        <group>
          <x-input title="账号" class="in" :max="5" v-model="user"
                   placeholder="请输入账号" :debounce="1000"></x-input>
        </group>
        <group>
          <x-input title="密码" class="in" type="password" v-model="password" placeholder="请输入密码"
                   is-type="china-password"></x-input>
        </group>
        <x-button type="warn" class="button" action-type="button" @click.native="username">登录</x-button>
      </div>
      <div class="third">
        <div class="hr"></div>
        <div class="font"><span>第三方登录</span></div>
        <div class="hr"></div>
      </div>
      <div class="icon">
        <i class="qq icon-qq"></i>
        <i class="weixin icon-weixin"></i>
        <i class="zhifubao icon-zhifubao"></i>
      </div>
    </div>
  </div>
</template>

<script>
  import {XInput, Group, XButton, Cell} from 'vux'
  export default{
    components: {
      XInput,
      XButton,
      Group,
      Cell
    },
    data () {
      return {
        user: '',
        password: ''
      }
    },
    methods: {
      username: function () {
        this.axios.post(this.$store.state.url, {
            userName: 12345,
            name: 11,
            age: 11
        }).then((res) => {
          console.log(res.data.age)
        })
      }
    }
  }
</script>

<style lang="less">
  @import "../../iconfont/fanhui/iconfont.css";
  @import "../../iconfont/qq/iconfont.css";
  @import "../../iconfont/weixin/iconfont.css";
  @import "../../iconfont/zhifu/iconfont.css";

  .login {
    background: url("../../images/bak.jpg") no-repeat;
    background-size: 100% 100%;
    height: 35.8em;
  }
  a{
    display: block;
  }

  .login-header {
    width: 100%;
    height: 2em;
    display: flex;
    justify-content: space-between;
  }

  .login-header > .left {
    flex: 1;
    height: 32px;
    text-align: center;
    margin-top: 5px;
  }

  .login-header > .center {
    flex: 1;
    margin-top: 5px;
    margin-left: -8px;
    font-size: 20px;
    color: #086929;
    text-align: center;
  }

  .login-header > .right {
    flex: 1;
    height: 32px;
    margin-top: 5px;
    font-size: 20px;
    text-align: center;
    color: #086929;
  }

  .login-input {
    height: 33.9em;
    width: 100%;
    background-color: rgba(0, 0, 0, 0.5);
  }

  .login-avatar {
    width: 100%;
    height: 160px;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .login-avatar > .avatar {
    border-radius: 50%;
    width: 130px;
    height: 130px;
    background: url("avatar.jpg");
    background-size: 100% auto;
  }

  .login-input > .input-height {
    height: 200px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
  }

  .in {
    background-color: rgba(0, 0, 0, 0.2);
  }

  .login-input > .input-height > .button {
    margin-top: 20px;
    width: 50%;
    background-color: rebeccapurple;
  }

  .login-input > .third {
    width: 100%;
    margin-top: 8px;
    height: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .login-input > .third > .hr {
    width: 30%;
    height: 1px;
    background: #2fedc4;
  }

  .login-input > .third > .font {
    font-size: 20px;
    color: #2fedc4;
  }

  .login-input > .icon {
    width: 100%;
    height: 50px;
    margin-top: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>
