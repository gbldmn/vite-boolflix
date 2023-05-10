<script>
import { store } from '../store'
export default {
    name: 'SingolaCard2',
    props: {
        infoSerieTv: Object
    },
    data(){
        return {
            store
        }
    }
}
</script>

<template>
        <div class="col-3">
        <div class="card position-relative mb-2">
            <img :src="store.pathImages + infoSerieTv.poster_path" class="card-img-top" alt="...">
            <div class="card-body position-absolute bg-white 2 ">
             <h5 class="card-title"> {{ infoSerieTv.name }} </h5>
             <p class="">{{ infoSerieTv.name }}</p>
             <p>{{ infoSerieTv.name }}</p>
             <p>{{ infoSerieTv.original_language }}</p>
             <p>{{ infoSerieTv.vote_average }}</p>
            </div>
        </div>

    </div>  
</template>