<template>
   <div class="container-fluid ml-5" style="margin-top: 5rem;">
      <div class="sharethis-inline-share-buttons"></div>
      <div class="row profile-cards-container">
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
         profileCards: []
      }
   },
   components: {
      ProfileCard
   },
   methods: {
      GoToProfilePage(data){
         console.log('parent');
         this.$emit('gotoProfilPage',data)
      },
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
   @media only screen and (max-width: 576px) {
      .profile-cards-container {
         justify-content: center;
      }
   }
</style>