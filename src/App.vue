<script>

import axios from 'axios'
import SearchComp from './components/SearchComp.vue'
import AreaFilm from './components/AreaFilm.vue'
import {store} from './store'


export default {
    name: "app",
    components: {
        SearchComp,
        AreaFilm,
    },  data(){
            return{
                store
            }
        },
        created(){
            // this.chiamataApiSerie()
            // this.chiamataApi()
        },
        methods: {

            chiamateApi() {
                axios.get(`https://api.themoviedb.org/3/search/tv?api_key=${ store.apiKey }&query=${ store.testoRicerca}`)
                .then((res)=> {

                    console.log(res.data.results)
                    store.arraySerieTv = res.data.results 
                })
                axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${ store.apiKey }&query=${ store.testoRicerca }`)
                .then((res)=> {
                    // console.log(res.data)

                   const datiApi = res.data.results
                    this.store.arrayFilm = datiApi
                    console.log(datiApi)
                })

            },

            // chiamataApi() {

            // }
        }
}

</script>

<template>

  <header class="containert p-3 d-flex justify-content-between aligh-items-center">
      <div class="rot">
           <h1 class="" > boolflix </h1>
           <SearchComp @nomeEmit="chiamateApi()"/>
      </div>
  </header>
  <main class="container p-3">

   <AreaFilm/>
  </main>

</template>

<style lang="scss">
@use './style/main.scss';


// richiesta api esempio movie
// https://api.themoviedb.org/3/movie/550?api_key=697c85f36243aecef552ab548222820c

// mia chiave api 
// 697c85f36243aecef552ab548222820c

</style>
