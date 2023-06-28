<script>
import AppPokedexScreen from './AppPokedexScreen.vue';
import {store} from '../data/store.js'
export default {
    components:{
        AppPokedexScreen,
    },
    data(){
        return{
            store,
        }
    },
}
</script>
<template lang="">
    <div>
        <div class="background">
            <div class="container">
                <div class="row">
                    <div class="col">
                        <div class="console">
                            <div class="buttonsGroup">
                                <div class="buttons">
    
                                </div>
                                <div class="buttons">
                                    
                                </div>
                                <div class="buttons">
                                    
                                </div>
                                <div class="buttons">
                                    
                                </div>
                            </div>
                            <select name="" id="" v-model='store.selectedType' @change="$emit('selectType')">
                                <option value="" selected>Select a type</option>
                                <option :value="type" v-for="(type, index) in store.pokemonTypes" :key="index">{{type}}</option>
                            </select>
                        </div>
                        <AppPokedexScreen />
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<style lang="scss" scoped>
    .background{
        background-color: rgb(183, 27, 27);
        padding-bottom: 25px;
        .console{
            display: flex;
            justify-content: space-between;
            padding: 25px 15px 20px;
            .buttonsGroup{
                display: flex;
            }
            .buttons{
                height: 40px;
                width: 40px;
                border-radius: 50%;
                border: 3px solid white;
                margin-right:15px;
            }
            .buttons:first-child{
                height: 80px;
                width: 80px;
                border: 4px solid white;
                background: rgb(51,51,255);
                background: linear-gradient(315deg, rgba(51,51,255,1) 25%, rgba(255,255,255,1) 100%);
            }
            .buttons:nth-child(2){
                background: rgb(255,51,51);
                background: linear-gradient(315deg, rgba(255,51,51,1) 25%, rgba(255,255,255,1) 100%);
            }
            .buttons:nth-child(3){
                background: rgb(255,255,51);
                background: linear-gradient(315deg, rgba(255,255,51,1) 25%, rgba(255,255,255,1) 100%);
            }
            .buttons:last-child{
                background: rgb(55,155,55);
                background: linear-gradient(315deg, rgba(55,155,55,1) 25%, rgba(255,255,255,1) 100%);
            }
            select{
                height: 100%;
                align-self: center;
                padding: 5px 10px;
            }
        }
    }
</style>