<template>
<<<<<<< HEAD
<div>
    <app-navbar></app-navbar>
    <app-loginRegister></app-loginRegister>
    <app-profileList></app-profileList>
    <app-profilePage></app-profilePage>
</div>
=======
   <ProfileList></ProfileList>
>>>>>>> profile list and card updated
</template>

<script>
import ProfileList from './views/profileList'
<<<<<<< HEAD
import Navbar from './views/Navbar'
import ProfilePage from './views/ProfilePage'
import LoginRegister from './views/login-register'
export default {
    name : 'app',
    data(){
        return {

        }
    },
    components : {
        'app-profilePage' : ProfilePage,
        'app-navbar' : Navbar,
        'app-profileList' : ProfileList,
        'app-loginRegister': LoginRegister
    }
=======

export default {
   components: {
      ProfileList
   }
>>>>>>> profile list and card updated
}
</script>


<style>
</style>