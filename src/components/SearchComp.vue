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
    <div>
        <input type="text" placeholder="cerca il tuo film" v-model="store.testoRicerca">
        <button  @click="$emit('nomeEmit')"> ricerca </button>
        <span v-for="(elem, index) in store.arrayDati"
        :key="index"> <br><strong>{{ elem.title }}</strong>  <br> {{ elem.original_title }} <br> {{ elem.original_language }} <br> {{ elem.vote_average }}</span>
    </div>
</template>


<style>

</style>