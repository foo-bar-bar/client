<template>
  <!-- card -->
  <div class="card border border-grey m-3 shadow-sm p-3 mb-1 bg-white rounded" style="width: 18rem;">
      <div class="image-container mb-2 mx-auto" v-bind:style="imageUrl"></div>
      <div class="card-body d-flex flex-column" id="card-body">
         <h5 class="card-title mx-auto">{{profileCard.userId.name}}</h5>
         <p class="card-text mx-auto">{{profileCard.age}}</p>
         <div class="justify-self text-center d-flex justify-around align-items-center">
            <a href="#" class="btn btn-primary text-center" @click.prevent="goToProfilePage(profileCard._id)">Cek profile!</a>
            <div class="fb-share-button" 
               v-bind:data-href="href"
               data-layout="button_count">
            </div>
         </div>
      </div>
   </div>
</template>

<script>
import axios from '../../apis/server'

(function(d, s, id) {
    var js, fjs = d.getElementsByTagName(s)[0];
    if (d.getElementById(id)) return;
    js = d.createElement(s); js.id = id;
    js.src = "https://connect.facebook.net/en_US/sdk.js#xfbml=1&version=v3.0";
    fjs.parentNode.insertBefore(js, fjs);
  }(document, 'script', 'facebook-jssdk'));

export default {
   props: ['profileCard'],
   data() {
      return {
         imageUrl: `background: url(\'${this.profileCard.image}\') no-repeat center center/cover;`,
         description: `Ayo cek profile ${this.profileCard.userId.name}!`,
         href: `${this.profileCard.image}`
      }
   },
   methods: {
      goToProfilePage(id){
         axios({
            method : 'get',
            url : `/profile/${id}`,
            headers : {
               'token' : localStorage.getItem('token')
            }
         })
         .then(({data})=>{
            console.log(data);
               console.log('cucu');
               this.$emit('GoToProfilePage',data)
         })
         .catch(err=>{
            console.log(err);
         })
      }
   }
}
</script>

<style scoped>
   .image-container {
      object-fit: fill;
      height: 13rem;
      width: 13rem;
      border-radius: 50%;
   }

   #card-body {
      border-top: 2px darkgrey solid;
   }

   .fb-share-button {
      margin-left: 1rem;
   }

   @media only screen and (max-width: 576px) {
      card {
         /* justify-self: center; */
         margin-left: auto;
         margin-right: auto;
      }
   }
</style>