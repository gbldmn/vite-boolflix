<script>
import { store } from '../store'
export default {
    name: 'SingolaCard',
    props: {
        infoFilm: Object,
        // infoSerieTv: Object
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
             <img :src="store.pathImages + infoFilm.poster_path" class="card-img-top" alt="...">
            <div class="card-body position-absolute bg-white  ">
             <h5 class="card-title"> {{ infoFilm.title }} </h5>
             <p class="">{{ infoFilm.original_title }}</p>
             <p>{{ infoFilm.title }}</p>
             <p>{{ infoFilm.original_language}}</p>
             <p>{{ infoFilm.vote_average }} <i class="fa-regular fa-star" style="color: #000000;"></i> </p>
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

    </div>  -->
</template>