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
        <button class="car"  @click="$emit('nomeEmit')"> <i class="fa-solid fa-magnifying-glass"></i> </button>
        <i class="fa-regular fa-bell mt-1 ms-2 fs-4" style="color: white;"></i>
        <i class="fa-regular fa-user mt-1 ms-2 fs-4" style="color: white;"></i>
    </div>
</template>


<style>

</style>