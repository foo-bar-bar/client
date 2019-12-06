<template>
   <div id="profile-list" class="container-fluid mt-3 ml-4">
      <!-- <Navbar></Navbar> -->
      <div class="row" id="profile-cards-container">
         <ProfileCard v-for="(profileCard, i) in profileCards" :key="i" :profileCard="profileCards[i]"></ProfileCard>
      </div>
   </div>
</template>

<script>
import axios from '../../apis/server'
import ProfileCard from '../components/card.vue'

export default {
   // props: [],
   data() {
      return {
         profileCards: [],
      }
   },
   components: {
      ProfileCard
   },
   methods: {
      fetchProfiles() {
         axios({
            url: `/profile`,
            method: 'get',
            headers: {
               token: localStorage.getItem('token')
            }
         })
         .then(({data}) => {
            this.profileCards = data
         })
      }
   },
   created() {
      this.fetchProfiles()
   }
}
</script>

<style>
   /* #profile-list { */
      /* background-color: black; */
   /* } */

   @media only screen and (max-width: 576px) {
      #profile-cards-container {
         justify-content: center;
      }
   }
</style>