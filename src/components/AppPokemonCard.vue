<script>
import {typesColor} from '../data/index.js'
export default {
    props:{
        pokemon: Object,
    },
    computed:{
        bgColor(){
            return typesColor[this.pokemon.type1]
        }
    },
}
</script>
<template lang="">
    <div>
        <div class="pokeCard" :style="`background-color: ${bgColor}`">
            <div class="img">
                <img :src="pokemon.imageUrl" :alt="pokemon.name">
            </div>
            <div class="details">
                <div class="number">
                    {{pokemon.number}}
                </div>
                <div class="name">
                    {{pokemon.name}}
                </div>
                <div class="type">
                    {{pokemon.type1}}
                    <span v-show="pokemon.type2 !== null">/ {{pokemon.type2}}</span>
                </div>
            </div>
        </div>
    </div>
</template>
<style lang="scss" scoped>
    .pokeCard{
        width: 100%;
        display: flex;
        flex-direction: column;
        padding: 20px 0;
        border-radius: 15px;
        margin: 10px 0;
        .img{
            align-self: center;
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background-color: white;
            img{
                border-radius: 50%;
                height: 100%;
                object-fit: contain;
            }
        }
        .details{
            text-align: center;
            .name{
                font-weight: bold;
            }
            .type{
                font-style: italic;
            }
        }
    }
</style>