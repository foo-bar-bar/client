<template>
  <div>
      <div class="card" style="width: 12rem;">
        <div class="card-body pt-1">
            <div class="rounded-circle mt-3 mx-auto mb-2"> </div>
            <p class="card-text mb-1" style="font-size:25px; font-weight: bold;">{{data.user.name}}</p>
            <hr class="m-0 mb-1">
            <p class="card-text mb-1" style="font-size: 13px;">Love Precentage</p>
            <button type="button" class="btn btn-primary"> {{data.value}}% </button>
        </div>
        <button type="button" class="btn btn-info btn-sm" style="margin-top: -5px;">
            <i class="fas fa-share"></i>
        </button> 
    </div>
  </div>
</template>

<script>
export default {
    props : ['data'],
}
</script>

<style>

</style>