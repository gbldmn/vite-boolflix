<script>
import { store } from '../store'
import SingolaCard from './SingolaCard.vue'

export default {
    name: 'AreaFilm',
    components: {
        SingolaCard,
    },
    data(){
        return {
            store
        }
    }
}
</script>

<template>
    <div class="row" v-if="store.arrayFilm.length">
        <h2 class="p-2"> <strong>Area Film</strong> </h2>
        <SingolaCard v-for="(film, index) in store.arrayFilm"
        :key="index"
        :info="film" />
    </div>
    <div class="row" v-if="store.arraySerieTv.length">
        <h2 class="p-2"> <strong>Area Serie Tv</strong> </h2>
        <SingolaCard v-for="(serie, index) in store.arraySerieTv"
        :key="index"
        :info="serie"/>
    </div>
</template>

<style lang="scss" scoped></style>