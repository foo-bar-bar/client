<template>
<div>
    <nav class="navbar navbar-expand-lg navbar-light fixed-top" style="background-color: palevioletred;">
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarTogglerDemo01" aria-controls="navbarTogglerDemo01" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarTogglerDemo01">
            <a class="navbar-brand ml-5" @click="home" style="color: white;" href="#">
                <i class="fas fa-heartbeat fa-2x" style="transform: rotate(-45deg);"></i>
                <span style="margin-left: -13px; ;font-size: 30px; font-weight: bold; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;"> LOVAPP </span>
            </a>
            <ul class="navbar-nav mx-auto">
                <!-- <button type="button" class="ml-5 btn btn-light mr-5"> -->
                    <!-- <i class="fas fa-arrow-left    "></i> -->
                    <!-- Back -->
                <!-- </button> -->
            </ul>
            <ul class="navbar-nav mr-auto mt-2 mt-lg-0"> </ul>
            <button type="button" class="btn btn-light mr-5" @click.prevent="logout">
                Logout
                <i class="fas fa-sign-out-alt"></i>
            </button>
        </div>
    </nav>
</div>
</template>

<script>
export default {
    methods: {
        logout() {
            this.$emit('userLogout')
        },
        home(){
            this.$emit('backHome')
        }
    }
}
</script>

<style>

</style>