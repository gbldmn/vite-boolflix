<script>
import { store } from '../store'
import SingolaCard from './SingolaCard.vue'

export default {
    name: 'AreaSerieTv',
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
     <!-- <div class="row">
        <SingolaCard v-for="(elem, index) in store.arraySerieTv"
        :key="index"
        :infoSerieTv="elem" />
    </div>  -->

</template>

<style lang="scss" scoped></style>