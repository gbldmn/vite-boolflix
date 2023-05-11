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
         },
         images(){
            if( this.info.poster_path){
                return `https://image.tmdb.org/t/p/w500/${this.info.poster_path}`
            } else if( this.info.poster_path === null )  {
                return '/images/virus-img-01.jpg'
            }
         },
         votoStelline(){
            return Math.ceil(this.info.vote_average / 2) 
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
        <div class="card position-relative mb-3">
             <img :src= " images() " class="card-img-top" alt="">
            <div class="card-body position-absolute bg-white 2 ">
             <h5 class="card-title"> {{ title() }} </h5>
             <p class="">{{ info.original_title }}</p>
             <p>{{ info.overview }}</p>
             <p>{{ info.original_language}} <img width="20" :src="bandiereStampate(info.original_language)" alt=""> </p>
             <p> voto: {{ votoStelline() }} <i v-for="n in 5" class="fa-star" :class=" ( n <= votoStelline() ) ? 'fa-solid' : 'fa-regular' " ></i> </p>
            </div>
        </div>

    </div>
</template>