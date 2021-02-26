<template>
  <div class="login-wrap">
    <el-form
      label-position="top"
      label-width="80px"
      :model="formLabelAlign"
      class="login-form"
    >
      <h2>用户登录</h2>
      <el-form-item label="用户名">
        <el-input v-model="formLabelAlign.username"></el-input>
      </el-form-item>
      <el-form-item label="密码">
        <el-input v-model="formLabelAlign.password"></el-input>
      </el-form-item>
      <el-button type="primary" class="login-btn" @click="login()"
        >登录</el-button
      >
    </el-form>
  </div>
</template>
<script>
export default {
  data () {
    return {
      formLabelAlign: {
        username: '',
        password: ''
      }
    }
  },
  methods: {
    login () {
      this.$http.post('login', this.formLabelAlign).then((res) => {
        console.log(res)
      })
    }
  }
}
</script>
<style scoped lang="scss">
.login-wrap {
  height: 100%;
  background-color: rgb(44, 44, 53);
  display: flex;
  justify-content: center;
  align-items: center;
  .login-form {
    width: 400px;
    background-color: #fff;
    border-radius: 5px;
    padding: 30px;
    .login-btn {
      width: 100%;
    }
  }
}
</style>
