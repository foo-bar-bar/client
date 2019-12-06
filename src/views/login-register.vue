<template>
  <div>
    <app-login v-if="pagelogin"></app-login>
    <app-register v-if="pageregister"></app-register>
  </div>
</template>


<script>
import Login from "../components/login";
import Register from "../components/register"
export default {
  data() {
    return {
      pagelogin : true,
      pageregister : false
    }
  },
  components: {
    "app-login": Login,
    "app-register": Register
  },
  methods: {
    checkLogin(){
      if(this.pagelogin){
        this.pagelogin = false
        this.pageregister = true
      } else {
        this.pagelogin = true
        this.pageregister = false
      }
    }
  }
}
</script>

<style>

</style>