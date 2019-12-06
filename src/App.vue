<template>
<div>
    <app-navbar></app-navbar>
    <app-profilePage></app-profilePage>
</div>
</template>

<script>
import Navbar from './views/Navbar'
import ProfilePage from './views/ProfilePage'
export default {
    name : 'app',
    data(){
        return {

        }
    },
    components : {
        'app-profilePage' : ProfilePage,
        'app-navbar' : Navbar
    }
}
</script>

<style>
</style>