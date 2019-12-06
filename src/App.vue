<template>
<div>
    <app-navbar></app-navbar>
    <app-loginRegister></app-loginRegister>
    <app-profileList></app-profileList>
    <app-profilePage></app-profilePage>
</div>
</template>

<script>
import ProfileList from './views/profileList'
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
}
</script>


<style>
</style>