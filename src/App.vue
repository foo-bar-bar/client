<template>
  <div>
    <app-login></app-login>
    <app-register></app-register>
  </div>
</template>

<script>
import BootstrapVue from 'bootstrap-vue';
import Login from "./components/login";
import Register from "./components/register"



export default {
  components: {
    "app-login": Login,
    "app-register": Register
  }
}
</script>


<style>

</style>