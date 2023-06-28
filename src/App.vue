<script>
import axios from 'axios';
import AppPokedex from './components/AppPokedex.vue';
import {store} from './data/store.js'
export default {
  components:{
    AppPokedex,
  },
  data(){
    return{
      store,
    }
  },
  mounted(){
    axios.get(store.api).then((response) =>{
      store.pokemonList= response.data.docs;
      store.loading= false;
    })
  },
  methods:{
    chooseType(){
      if(store.selectedType=== ''){
        axios.get(store.api).then((response) =>{
        store.pokemonList= response.data.docs;
        store.loading= false;
      })
      } else {
        store.pokemonList= '';
        axios.get(store.api + 'eq[type1]=' + store.selectedType).then((response) =>{
        store.pokemonList= response.data.docs;
        store.loading= false;
      })
      }
    }
  }
}
</script>
<template lang="">
  <div>
    <AppPokedex @selectType="chooseType"/>
  </div>
</template>
<style lang="scss">
  @use './styles/generals.scss' as *;
</style>