<script>
 import { store } from '../store'
 export default {
    name: 'SingolaCard',
    props: {
        info: Object
    },
     methods: {
         bandiereStampate(x) {
             x = x.toUpperCase();

             if( x == 'EN'){
                 x = 'GB'
                 return `https://flagsapi.com/${x}/shiny/64.png`
             } else {
                 return `https://flagsapi.com/${x}/shiny/64.png`
                }
         },
         title(){
            if(this.info.original_title){
                return this.info.original_title
            } else {
                return this.info.original_name
            }
         }
     },
    data(){
        return{
            store
        }
    }
 }
</script>

<template>
     <div class="col-3">
        <div class="card position-relative mb-2">
             <img :src= "`https://image.tmdb.org/t/p/w342/${info.poster_path}`" class="card-img-top" alt="">
            <div class="card-body position-absolute bg-white 2 ">
             <h5 class="card-title"> {{ title() }} </h5>
             <p class="">{{ info.original_title }}</p>
             <p>{{ info.title }}</p>
             <p>{{ info.original_language}} <img width="20" :src="bandiereStampate(info.original_language)" alt=""> </p>
             <p>{{ info.vote_average }} <i class="fa-regular fa-star" style="color: #000000;"></i> </p>
            </div>
        </div>

    </div>
      <!-- <div class="col-3">
        <div class="card">
             <img src="" class="card-img-top" alt="...">
            <div class="card-body">
             <h5 class="card-title"> {{ infoSerieTv.name }} </h5>
             <p class="">{{ infoSerieTv.name }}</p>
             <p>{{ infoSerieTv.name }}</p>
             <p>{{ infoSerieTv.language }}</p>
             <p>{{ infoSerieTv.vote_average }}</p>
            </div>
        </div>

    </div>   -->
</template>