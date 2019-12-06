<template>
<div>
    <app-navbar @userLogout="userLogout" @backHome="backHome"></app-navbar>
    <!-- <app-uploadImage></app-uploadImage> -->
    <app-loginRegister @goToProfileList="goToProfileList" v-if="!isLoggedIn" v-show="isLogin"></app-loginRegister>
    <app-profileList @gotoProfilPage="gotoProfilPage" v-if="isLoggedIn" ></app-profileList>
    <app-profilePage  v-if="isProfilePage" :dataUser="dataUser"></app-profilePage>
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
            isLogin : false,
            isLoggedIn: false,
            isProfilePage: false,
            dataUser : {}
        }
    },
    components : {
        'app-profilePage' : ProfilePage,
        'app-navbar' : Navbar,
        'app-profileList' : ProfileList,
        'app-loginRegister': LoginRegister,
        'app-uploadImage': UploadImage
    },
    methods: {
        backHome(){
            this.isProfilePage = false
            this.isLoggedIn = true
        },
        goToProfileList() {
            this.isLoggedIn = true
        },
        gotoProfilPage(data) {
            this.dataUser = data
            this.isProfilePage = true
            this.isLoggedIn = false
            this.isLogin = false
        },
        userLogout() {
            console.log('emit diterima')
            this.isLoggedIn = false,
            this.isLogin = true ,
            this.isProfilePage= false
            localStorage.removeItem('name')
            localStorage.removeItem('token')
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