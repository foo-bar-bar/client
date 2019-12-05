<template>
   <div id="profile-list" class="container mt-3">
      <div class="row">
         <ProfileCard v-for="(profileCard, i) in profileCards" :key="i" :profileCards="profileCards"></ProfileCard>
      </div>
   </div>
  
</template>

<script>
import ProfileCard from '../components/card.vue'
import axios from 'axios'

export default {
   // props: [],
   data: {
      profileCards: [{

      }]
   },
   components: {
      ProfileCard
   },
   methods: {
      fetchProfiles() {

      }
   }
}
</script>

<style>

</style>