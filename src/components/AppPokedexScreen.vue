<script>
import AppPokemonCard from './AppPokemonCard.vue';
import {store} from '../data/store.js';
export default {
    components:{
        AppPokemonCard,
    },
    data(){
        return{
            store
        }
    },
}
</script>
<template lang="">
    <div>
        <div class="screenContainer">
            <div class="screenContent">
                <AppPokemonCard class="pokemonCard" v-for="(pokemon, index) in store.pokemonList" :key="index" :pokemon="pokemon" />
            </div>
        </div>
    </div>
</template>
<style lang="scss" scoped>
    .screenContainer{
        background-color: rgb(222, 222, 222);
        padding: 40px 20px;
        border-radius: 20px;
        .screenContent{
            background-color: rgb(104, 108, 112);
            padding:10px;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            .pokemonCard{
                width: calc(100% / 5 - 15px);
            }
        }
    }
</style>