<template>
  <div>
    <app-login
      v-if="formLogin"
      :formLogin="formLogin"
      :formRegister="formRegister"
      @checkLogin="checkLogin"
      @loginSuccess="loginSuccess"
    ></app-login>
    <app-register
      v-if="formRegister"
      :formLogin="formLogin"
      :formRegister="formRegister"
      @checkLogin="checkLogin"
    ></app-register>
  </div>
</template>


<script>
import Login from "../components/login";
import Register from "../components/register"
export default {
  data() {
    return {
<<<<<<< HEAD
      pagelogin : true,
      pageregister : false
=======
      formLogin: true,
      formRegister: false,
>>>>>>> development
    }
  },
  components: {
    "app-login": Login,
    "app-register": Register
  },
  methods: {
<<<<<<< HEAD
    checkLogin(){
      if(this.pagelogin){
        this.pagelogin = false
        this.pageregister = true
      } else {
        this.pagelogin = true
        this.pageregister = false
      }
=======
    checkLogin(login, register) {
      this.formLogin = login;
      this.formRegister = register
    },
    loginSuccess() {
      console.log('di loginSuccess')
      this.$emit('goToProfileList')
>>>>>>> development
    }
  }
}
</script>

<style>

</style>