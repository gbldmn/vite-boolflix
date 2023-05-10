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
    <div class="row">
        <SingolaCard v-for="(elem, index) in store.arrayFilm"
        :key="index"
        :infoFilm="elem" />
    </div>

</template>

<style lang="scss" scoped></style>