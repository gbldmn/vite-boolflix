<script>

import axios from 'axios'
import SearchComp from './components/SearchComp.vue'
import {store} from './store'


export default {
    name: "app",
    components: {
        SearchComp,
    },  data(){
            return{
                store
            }
        },
        created(){
            this.chiamataApi()
        },
        methods: {
            chiamataApi() {
                // axios.get(`https://api.themoviedb.org/3/search/tv?api_key=697c85f36243aecef552ab548222820c&query=${ store.testoRicerca}`)
                // .then((res)=> {
                //    const datiApi = res.data.results
                //     this.store.arrayDati = datiApi
                // })
                axios.get(`https://api.themoviedb.org/3/search/movie?api_key=697c85f36243aecef552ab548222820c&query=${ store.testoRicerca }`)
                .then((res)=> {
                    // console.log(res.data)

                   const datiApi = res.data.results
                    this.store.arrayDati = datiApi
                    console.log(datiApi)
                })
            }
        }
}

</script>

<template>
<SearchComp @nomeEmit="chiamataApi" class="container"/>
  
</template>

<style lang="scss">
@use './style/main.scss';


// richiesta api esempio movie
// https://api.themoviedb.org/3/movie/550?api_key=697c85f36243aecef552ab548222820c

// mia chiave api 
// 697c85f36243aecef552ab548222820c

</style>
