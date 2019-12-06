<template>
   <div>
   <div class="card mr-3" style="width: 18rem;">
      <img src="../../assets/cat1.jpg" class="card-img-top" alt="">
      <div class="card-body">
         <h5 class="card-title" style="font-weight: bold;">Name</h5>
         <p class="card-text">
            Siapa saya
         </p>
         <div class="d-flex justify-content-center">
            <a href="#" class="btn btn-sm btn-primary">
               <i class="fas fa-sign-in-alt    "></i>
               Profile
            </a>
            <a href="#" class="btn btn-sm btn-primary ml-2">
               <i class="fas fa-heart"></i>
            </a>
         </div>
      </div>
   </div>
</template>

<script>
export default {
   props: ['profileCards']
}
</script>

<style>

</style>