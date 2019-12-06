<template>
  <div
      id="signin"
      class="mt-5 container justify-content-center border rounded-sm bg-light p-0"
      style="width:30%; height:85vh"
    >
    <b-form id="signin-form" v-on:submit.prevent="onSubmit" class="p-3">
      <h1 class="h3 my-3 font-weight-normal text-center">Sign In</h1>
      <b-form-group
        label="Email address:"
        label-for="signin-email"
      >
        <b-form-input
          id="signin-email"
          type="email"
          v-model="email"
          required
          placeholder="Enter email"
        ></b-form-input>
      </b-form-group>

      <b-form-group
        label="Password:"
        label-for="signin-password"
      >
        <b-form-input
          id="signin-password"
          type="password"
          v-model="password"
          required
          placeholder="Enter password"
        ></b-form-input>
      </b-form-group>

      <button class="btn btn-lg btn-primary btn-block btn-sm" type="submit">Sign In</button>
      <p class="mt-2 text-center text-secondary">Don't have an account? <a href="#" @click.prevent="checkLogin" >Register</a></p>
    </b-form>
    <div class="mx-0 copyright">
      <p class=" text-muted">&copy; 2019</p>
    </div>
  </div>
</template>

<script>
import axios from "../../apis/server"
import Swal from 'sweetalert2'

export default {
  props: ["formLogin", "formRegister"],
  name: "login",
  data () {
    return {
      email: "",
      password: ""
    }
  },
  methods: {
    onSubmit() {
      axios({
        method: "post",
        url: "/user/login",
        data: {
          email: this.email,
          password: this.password
        }
      })
        .then(({ data })=> {
          localStorage.setItem("token", data.token)
          this.$emit("checkLogin", false, false)
          this.$emit('loginSuccess')
          Swal.fire({
            icon: 'success',
            text: "Successfully signed in!"
          })
        })
        .catch(err => {
          Swal.fire({
            icon: 'error',
            title: 'Oops...',
            text: "Invalid email/password!"
          })
        })
    },
    checkLogin() {
      if (this.formLogin) {
        this.$emit("checkLogin", false, true);
      } else {
        this.$emit("checkLogin", true, false);
      }
      console.log(this.formLogin, this.formRegister)
    }
  }
}
</script>

<style scoped>
 h1 {
   font-family: 'Solway', serif;
 }

  #signin {
    position: relative;
    background-color:bisque
  }

 .copyright {
   font-size: 0.8em;
   text-align: center;
   width: 100%;
   display: inline-block;
   position: absolute;
   bottom: 0
 }
</style>