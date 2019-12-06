<template>
  <!-- card -->
  <div class="card border border-grey m-3 shadow-sm p-3 mb-1 bg-white rounded" style="width: 18rem;">
      <div class="image-container mb-2 mx-auto" v-bind:style="imageUrl">
         <!-- <img :src="profileCard.image" class="card-img-top border-bottom border-dark pb-2 rounded-circle" alt="cat"> -->
      </div>
      <div class="card-body d-flex flex-column" id="card-body">
         <h5 class="card-title mx-auto">{{profileCard.userId.name}}</h5>
         <p class="card-text mx-auto">{{profileCard.age}}</p>
         <div class="justify-self text-center">
            <a href="#" class="btn btn-primary text-center" @click.prevent="goToProfilePage(profileCard._id)">Cek profile!</a>
         </div>
      </div>
   </div>
</template>

<script>
import axios from '../../apis/server'
export default {
   props: ['profileCard'],
   data() {
      return {
         imageUrl: `background: url(\'${this.profileCard.image}\') no-repeat center center/cover;`
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

   @media only screen and (max-width: 576px) {
      card {
         /* justify-self: center; */
         margin-left: auto;
         margin-right: auto;
      }
   }
</style>