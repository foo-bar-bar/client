<template>
   <div class="mt-5">
      <div id="profile-list" class="container">
      <div class="row mt-5">
         <profile-card
            v-for="(profileCard, i) in profileCards" :key="i"
            :profileCards="profileCards">
         </profile-card>
      </div>
   </div>
   </div>
</template>

<script>
import ProfileCard from '../components/card'
import axios from 'axios'

export default {
   // props: [],
   data() {
      return {
         profileCards: [{
         text : ""
      }]
      }
   },
   components: {
      'profile-card' : ProfileCard
   },
   methods: {
      fetchProfiles() {

      }
   }
}
</script>

<style>

</style>