<script>
import AppPokemonCard from './AppPokemonCard.vue';
import AppLoader from './AppLoader.vue';
import {store} from '../data/store.js';
export default {
    components:{
        AppPokemonCard,
        AppLoader
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
                <AppPokemonCard class="pokemonCard" v-for="(pokemon, index) in store.pokemonList" :key="index" :pokemon="pokemon" v-if="store.loading===false"/>
                <div class="loaderDisplay" v-else>
                    <AppLoader class="Loader" />
                </div>
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
            overflow-y: scroll;
            height: 530px;
            .pokemonCard{
                width: calc(100% / 5 - 15px);
            }
        }
    }
    .loaderDisplay{
        width: 100%;
        height: 100%;
        display: flex;
        align-content: center;
        justify-content: center;
        .Loader{
            align-self: center;
        }
    }
</style>