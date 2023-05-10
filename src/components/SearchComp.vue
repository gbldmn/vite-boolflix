<script>
import {store} from '../store'

export default {
    name: "SearchComp",
    data(){
        return {
            store
        }
    }
}
</script>



<template>
    <div class="d-flex aligh-items-center car">
        <input type="text" placeholder="cerca il tuo film o serie tv" v-model="store.testoRicerca">
        <button class="car"  @click="$emit('nomeEmit')"> ricerca </button>
        <!-- <span v-for="(elem, index) in store.arrayFilm"
        :key="index"> <br><strong>{{ elem.title }}</strong>  <br> {{ elem.original_title }} <br> {{ elem.original_language }} <br> {{ elem.vote_average }}</span> -->
    </div>
</template>


<style>

</style>