<template>
  <div class="loginContainer">
    <div class="loginBox">
<!--      头像区域-->
      <div class="avatarBox">
        <img src="../assets/logo.png" alt="">
      </div>
<!--      表单区域-->
      <el-form
        class="loginForm"
        :model="loginForm"
        :rules="loginFormRules">
<!--        用户名-->
        <el-form-item
          prop="username">
          <el-input
            v-model="loginForm.username"
            prefix-icon="el-icon-user-solid">
          </el-input>
        </el-form-item>
<!--        密码-->
        <el-form-item
          prop="password">
          <el-input
            v-model="loginForm.password"
            prefix-icon="el-icon-key"
            type="password">
          </el-input>
        </el-form-item>
<!--        按钮区域-->
        <el-form-item class="btns">
          <el-button type="primary">登录</el-button>
          <el-button type="info">重置</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
      // 登录表单数据绑定对象
      loginForm: {
        username: 'zs',
        password: '123'
      },
      // 表单验证规则对象
      loginFormRules: {
        // 验证用户名
        username: [
          { required: true, message: '请输入用户名', trigger: 'blur' },
          { min: 3, max: 10, message: '长度在 3 到 10 个字符', trigger: 'blur' }
        ],
        // 验证密码
        password: [
          { required: true, message: '请输入密码', trigger: 'blur' },
          { min: 6, max: 15, message: '长度在 6 到 15 个字符', trigger: 'blur' }
        ]
      }
    }
  }
}
</script>

<style lang="less" scoped>

  .loginContainer{
    background-color: #2b4b6b;
    height: 100%;
  }

  .loginBox{
    width: 450px;
    height: 300px;
    background-color: #FFFFFF;
    border-radius: 3px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);

    .avatarBox{
      height: 130px;
      width: 130px;
      border: 1px solid #EEEEEE;
      border-radius: 50%;
      padding: 10px;
      box-shadow: 0 0 10px #DDDDDD;
      position: absolute;
      left: 50%;
      transform: translate(-50%, -50%);
      background-color: #FFFFFF;

      img{
        width: 100%;
        height: 100%;
        background-color: #EEEEEE;
        border: 1px solid #EEEEEE;
        border-radius: 50%;
      }
    }
  }

  .btns{
    display: flex;
    justify-content: flex-end;
  }

  .loginForm{
    position: absolute;
    bottom: 0;
    width: 100%;
    padding: 0 20px;
    box-sizing: border-box;
  }
</style>
