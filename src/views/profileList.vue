<template>
   <div id="profile-list" class="container-fluid mt-3 ml-4">
      <!-- <Navbar></Navbar> -->
      <div class="row" id="profile-cards-container">
         <ProfileCard v-for="(profileCard, i) in profileCards" :key="i" :profileCard="profileCards[i]"></ProfileCard>
      </div>
   </div>
   </div>
</template>

<script>
// import Navbar from '../components/navbar'
import ProfileCard from '../components/card.vue'
import axios from 'axios'

export default {
   // props: [],
   data() {
      return {
         profileCards: [
            {
               name: "Dedi Prakasa",
               profileDescription: "Aku malu dan gak mau",
               image: "../../assets/cat1.jpg"
            },
            {
               name: "Daniel Evan",
               profileDescription: "Aku malu malu lagi",
               image: "../../assets/cat1.jpg"
            },
            {
               name: "Dedi Prakasa",
               profileDescription: "Aku malu dan gak mau",
               image: "../../assets/cat1.jpg"
            },
            {
               name: "Daniel Evan",
               profileDescription: "Aku malu malu lagi",
               image: "../../assets/cat1.jpg"
            },
            {
               name: "Dedi Prakasa",
               profileDescription: "Aku malu dan gak mau",
               image: "../../assets/cat1.jpg"
            },
            {
               name: "Daniel Evan",
               profileDescription: "Aku malu malu lagi",
               image: "../../assets/cat1.jpg"
            },
         ]
      }
   },
   components: {
      Navbar,
      ProfileCard
   },
   methods: {
      fetchProfiles() {

      }
   }
}
</script>

<style>
   #profile-list {
      /* background-color: black; */
   }

   @media only screen and (max-width: 576px) {
      #profile-cards-container {
         justify-content: center;
      }
   }
</style>