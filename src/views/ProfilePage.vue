<template>
<div>
    <div class="row">
        <div class="col" >
            <div class="container">
                <div class="jumbotron jumbotron-fluid">
                    <div class="container mt-5 text-center">
                        <div class="rounded-circle mx-auto" style="height: 260px; border: 7px solid rgba(0, 0, 0, 0.473); width: 260px; background-color: brown; background-size:100%;"> </div>
                        <div class="d-flex align-items-center justify-content-center">
                            <span style="font-size: 40px; font-weight: bold;" >Name</span>
                        </div>
                        <div class="accordion" id="accordionExample">
                        <div class="container" style="width: 40em;">
                        <div class="card">
                            <div class="card-header p-1" id="headingOne">
                                <h2 class="mb-0 d-flex flex-row pb-1">
                                    <button class="btn btn-info mt-2 px-5" style="margin-left: 14em;" type="button" data-toggle="collapse" data-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
                                        Details
                                    </button>
                                    <div class="ml-auto">
                                        <button type="button" class="mt-1 btn btn-primary btn-sm">
                                            <i class="fas fa-heart"></i>
                                        </button>
                                        <button type="button" class="mr-1 mt-1 btn btn-primary btn-sm">
                                            <i class="fas fa-share    "></i>
                                        </button>   
                                    </div>
                                </h2>
                            </div>
                            <div id="collapseOne" class="collapse show" aria-labelledby="headingOne" data-parent="#accordionExample">
                                <div class="card-body d-flex flex-row justify-content-center">
                                    <div class="card ml-1" style="width: 100%; height: auto;">
                                        <div class="card-body pt-1">
                                            <h5 class="card-title mt-2"  style="font-size: 25px; font-weight: bold;"> Age </h5>
                                            <button type="button" style="font-size: 15px;" class="btn btn-sm btn-primary px-5"> 90th </button>
                                            <hr>
                                            <h5 class="card-title mt-2"  style="font-size: 25px; font-weight: bold;"> Multicultural </h5>
                                            <button type="button" style="font-size: 15px;" class="btn btn-sm btn-primary px-5"> RAss </button>
                                            <hr>
                                            <h5 class="card-title mt-2"  style="font-size: 25px; font-weight: bold;"> Feminime </h5>
                                            <button type="button" style="font-size: 15px;" class="btn btn-sm btn-secondary px-5"> lorem </button>
                                            <hr>
                                            <h5 class="card-title mt-2"  style="font-size: 25px; font-weight: bold;"> Masculine </h5>
                                            <button type="button" style="font-size: 15px;" class="btn btn-sm btn-secondary px-5"> RAss </button>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                        </div>
                        <hr class="my-2">
                        <p class="text-left ml-5" style="font-size: 20px;">
                            <i class="fas fa-info-circle    "></i>
                            More info rank
                        </p>
                        <div class="row d-flex align-items-center justify-content-center">
                            <div class="col-3 mr-4 mt-1">
                                <div class="card" style="width: 12rem;">
                                    <div class="card-body pt-1">
                                        <div class="rounded-circle mt-3 mx-auto mb-2" style="height: 130px; width: 130px; background-color: brown; background-size:100%;"> </div>
                                        <p class="card-text mb-1" style="font-size: 20px; font-weight: bold;">Name</p>
                                        <hr class="m-0 mb-1">
                                        <p class="card-text mb-1" style="font-size: 13px;">Love Precentage</p>
                                        <button type="button" class="btn btn-primary"> 78% </button>
                                    </div>
                                    <button type="button" class="btn btn-info btn-sm" style="margin-top: -5px;">
                                        <i class="fas fa-share"></i>
                                    </button> 
                                </div>
                            </div>                                    
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {

}
</script>

<style>

</style>