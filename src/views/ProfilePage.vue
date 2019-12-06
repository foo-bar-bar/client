<template>
<div>
    <div class="row">
        <div class="col" >
            <div class="container">
                <div class="jumbotron jumbotron-fluid">
                    <div class="container mt-5 text-center">
                        <div class="rounded-circle mx-auto" :style="imageStyle"> </div>
                        <div class="d-flex align-items-center justify-content-center">
                            <span style="font-size: 40px; font-weight: bold;" >{{dataUser.userId.name}}</span>
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
                                        <button type="button" @click.prevent="loveme(dataUser._id, dataUser.userId.name)" class="mt-1 btn btn-primary btn-sm">
                                            <i class="fas fa-heart"></i>
                                            {{(dataUser.lovers.length)}}
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
                                            <button type="button" style="font-size: 15px;" class="btn btn-sm btn-primary px-5"> {{dataUser.age}}th </button>
                                            <hr>
                                            <h5 class="card-title mt-2"  style="font-size: 25px; font-weight: bold;"> Multicultural </h5>
                                            <button type="button" style="font-size: 15px;" class="btn btn-sm btn-primary px-5"> {{dataUser.multicultural}} </button>
                                            <hr>
                                            <h5 class="card-title mt-2"  style="font-size: 25px; font-weight: bold;"> Feminine </h5>
                                            <button type="button" style="font-size: 15px;" class="btn btn-sm btn-secondary px-5"> {{Math.round(dataUser.feminine * 100)}}% </button>
                                            <hr>
                                            <h5 class="card-title mt-2"  style="font-size: 25px; font-weight: bold;"> Masculine </h5>
                                            <button type="button" style="font-size: 15px;" class="btn btn-sm btn-secondary px-5"> {{Math.round(dataUser.masculine * 100)}}%</button>
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
                        <div class="row d-flex">
                            <div class="col-3 mt-1" v-for="data in dataUser.lovers" :key="data._id">
                                <div class="card" style="width: 12rem;">
                                    <profile-rank :data="data"></profile-rank>
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
import LoveRank from '../components/LoveRank'
import axios from '../../apis/server'
export default {
    props : ['dataUser'],
    data() {
        return {
            imageStyle : `height: 260px; border: 7px solid rgba(0, 0, 0, 0.473); width: 260px; background: url('${this.dataUser.image}') no-repeat center center/cover; background-size:100%`
        }
    },
    methods: {
        loveme(id,name){
            axios({
            method : 'patch',
            url : `/profile/love/${id}`,
            headers : {
                'token' : localStorage.getItem('token')
            },
            data : {
                fname : localStorage.getItem('name'),
                sname : name
            }
            })
            .then(({data})=>{
                this.dataUser.lovers = data.profile.lovers
            })
            .catch(err=>{
                console.log(err);
            })
        }
    },
    components :{
        'profile-rank' : LoveRank
    }
}
</script>

<style>

</style>