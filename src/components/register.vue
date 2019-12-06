<template>
  <div
      id="register"
      class="mt-5 container justify-content-center border rounded-sm bg-light p-0"
      style="width:30%; "
    >
      <b-form id="register-form" class="p-3">
        
        <h1 class="h3 my-3 font-weight-normal text-center">Register</h1>

        <b-form-group
          label="Name:"
          label-for="reg-name"
        >
          <b-form-input
            id="reg-name"
            type="text"
            v-model="name"
            required
            placeholder="Enter your name"
          ></b-form-input>
        </b-form-group>

        <b-form-group
          label="Email address:"
          label-for="reg-email"
        >
          <b-form-input
            id="reg-email"
            type="email"
            v-model="email"
            required
            placeholder="Enter email"
          ></b-form-input>
        </b-form-group>

        <b-form-group
          label="Password:"
          label-for="reg-password"
        >
          <b-form-input
            id="reg-password"
            type="text"
            v-model="password"
            required
            placeholder="Enter your password"
          ></b-form-input>
        </b-form-group>


        
          <button class="btn btn-lg btn-primary btn-block btn-sm" type="submit">Register</button>
          <p class="mt-2 text-center text-secondary">Already have an account?<a href="#"> Sign in</a></p>
        </b-form>
        <div class="mx-0 copyright">
          <p class=" text-muted">&copy; 2019</p>
        </div>
    </div>
</template>

<script>
export default {
  name: "register",
  data () {
    return {
      name: "",
      email: "",
      password: "",
    }
  }
}
</script>

<style scoped>
  
  h1 {
   font-family: 'Solway', serif;
 }

  #register {
    position: relative;
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