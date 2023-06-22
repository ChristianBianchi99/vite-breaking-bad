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
    })
  }
}
</script>
<template lang="">
  <div>
    <AppPokedex />
  </div>
</template>
<style lang="scss">
  
</style>