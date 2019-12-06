<template>

   <div id="profile-list" class="container-fluid mt-3 ml-4">
      <!-- <Navbar></Navbar> -->
      <div class="upload-img">
         <b-form class="basic">
         <b-form-file
            v-model="file"
            :state="Boolean(file)"
            placeholder="Choose a file or drop it here..."
         >
         </b-form-file>
         <br>
         <button type="submit" class="btn btn-primary" @click.prevent="uploadImage">Upload</button>
         </b-form>

      </div>
      <div class="row" id="profile-cards-container">
   
         <!-- <button >Upload Image</button> -->
         <ProfileCard @GoToProfilePage="GoToProfilePage" v-for="(profileCard, i) in profileCards" :key="i" :profileCard="profileCards[i]"></ProfileCard>

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

         profileCards: [],
         file: null


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
         .catch(err => {
            console.log(err)
         })
      },
      uploadImage() {
      console.log(this.file)
      let fd = new FormData()

      fd.append("image", this.file)
      console.log(fd)
      axios({
        url: "/profile",
        method: "post",
        data: fd,
        headers: {
          token: localStorage.getItem("token")
        }
      })
        .then(({data}) => {
          console.log(data)
          this.fetchProfiles()
          
        })
        .catch(err => {
          console.log(err)
        })
    }
   },
   created() {
      this.fetchProfiles()
   },
   computed() {
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