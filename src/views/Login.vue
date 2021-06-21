<template>
  <div class="login_page">
    <div class="login">
      <h1 v-if="isShow">Login</h1>
      <h1 v-else>注册</h1>
      <el-form :model="loginForm" ref="loginRef" v-if="isShow">
        <el-form-item label="用户名：" label-width="120px">
          <el-input v-model.trim="loginForm.username" placeholder="请输入用户名"></el-input>
        </el-form-item>
        <el-form-item label="密 码：" label-width="120px">
          <el-input v-model.trim="loginForm.password" placeholder="请输入密码" type="password"></el-input>
        </el-form-item>
        <el-row>
          <el-col :span="12" :push="3">
          <el-link type="primary" @click="toRegist">注册</el-link>
          </el-col>
          <el-col :span="12">
             <el-form-item class="btn_group">
              <el-button type="primary" @click="login">登陆</el-button>
              <el-button @click="resetForm">重置</el-button>
            </el-form-item>
          </el-col>
        </el-row>
      </el-form>
      <el-form :model="registForm" ref="registRef" v-if="!isShow">
        <el-form-item label="用户名：" label-width="120px">
          <el-input v-model.trim="registForm.username" placeholder="请输入用户名"></el-input>
        </el-form-item>
        <el-form-item label="密 码：" label-width="120px">
          <el-input v-model.trim="registForm.password" placeholder="请输入密码" type="password"></el-input>
        </el-form-item>
        <el-form-item class="btn_group">
          <el-button type="primary" @click="regist">注册</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>
<script>
import { mapState } from 'vuex'
import { dateFormat } from '@/utils'
  export default {
    name: 'Login',
    data() {
      return {
        loginForm: {
          username: '',
          password: ''
        },
        registForm: {
          username: '',
          password: ''
        },
        isShow: true
      }
    },
    methods: {
      login() {
        const users = this.users
        const { username, password } = this.loginForm
        const hasUser = users.find(item => {
          return item.username == username && item.password == password
        })
        if(hasUser) {
          if(hasUser.username === 'admin') {
            sessionStorage.setItem('isAdmin', true)
            this.$store.commit('SET_ADMIN', true)
          }else {
            sessionStorage.setItem('isAdmin', false)
            this.$store.commit('SET_ADMIN', false)
          }
          sessionStorage.setItem('user', this.loginForm.username)
          this.$store.commit('SET_USER', this.loginForm.username)
          this.$router.push('/home')
        }else {
          this.$message.error('帐号密码不正确，请重新输入！')
        }
      },
      regist() {
        const { username, password } = this.registForm
        if(!username || !password) {
          this.$message.error('请输入注册信息');
          return
        }
        this.$store.commit('SET_USERS', {
            username,
            password,
            date: dateFormat("YYYY-mm-dd HH:MM", new Date)
          })
        this.$message({
          type: 'success',
          message: '注册成功！'
        })
        this.isShow = !this.isShow
      },
      toRegist() {
        this.registForm.username = ''
        this.registForm.password = ''
        this.isShow = !this.isShow
      },
      resetForm() {
        this.loginForm.username = ''
        this.loginForm.password = ''
      }
    },
    computed: {
      ...mapState({
        users: state => state.users
      })
    }
    
  }
</script>

<style lang="scss" scoped>
.login_page {
  background: url('../assets/imgs/bgc.jpg') no-repeat center/cover;
  height: 100%;
  width: 100%;
  .login {
    width: 500px;
    height: 300px;
    border: 1px solid #eee;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: #fff;
    box-shadow: 0 0 10px;
    padding-right: 20px;
    h1 {
      text-align: center;
      margin-bottom: 40px;
    }
    .btn_group {
      display: flex;
      justify-content: flex-end;
    }
  }
}
</style>
