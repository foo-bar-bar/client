<template>
<div>
    <app-navbar @userLogout="userLogout"></app-navbar>
    <app-loginRegister @goToProfileList="goToProfileList" v-if="!isLoggedIn"></app-loginRegister>
    <app-profileList v-if="isLoggedIn"></app-profileList>
    <app-profilePage v-if="isProfilePage"></app-profilePage>
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
            isLoggedIn: false,
            isProfilePage: false
        }
    },
    components : {
        'app-profilePage' : ProfilePage,
        'app-navbar' : Navbar,
        'app-profileList' : ProfileList,
        'app-loginRegister': LoginRegister
    },
    methods: {
        goToProfileList() {
            this.isLoggedIn = true
        },
        userLogout() {
            console.log('emit diterima')
            this.isLoggedIn = false
        }
    },
    created() {
        if(localStorage.getItem('token') !== null) {
            this.isLoggedIn = true
        }
    }
}
</script>


<style>
</style>