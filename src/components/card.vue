<template>
  <!-- card -->
  <div class="card border border-grey m-3 shadow-sm p-3 mb-1 bg-white rounded" style="width: 18rem;">
      <img src="../../assets/cat1.jpg" class="card-img-top border-bottom border-dark pb-2" alt="cat">
      <div class="card-body d-flex flex-column">
         <h5 class="card-title">{{profileCard.name}}</h5>
         <p class="card-text">{{profileCard.profileDescription}}</p>
         <div class="justify-self text-center">

            <a href="#" class="btn btn-primary text-center">Cek profileku!</a>
         </div>
      </div>
   </div>
</template>

<script>
export default {
   props: ['profileCard']
}
</script>

<style>

</style>