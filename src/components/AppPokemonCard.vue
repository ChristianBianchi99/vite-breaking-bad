<script>
export default {
    props:{
        pokemon: Object,
    },
    methods:{
        pokemonType(type1){
            switch(type1){
                case 'Grass':
                    return 'green';
                    break;
                case 'Fire':
                    return 'red';
                    break;
                case 'Water':
                    return 'blue';
                    break;
                case 'Bug':
                    return '';
                    break;
                case 'Normal':
                    return '';
                    break;
                case 'Flying':
                    return '';
                    break;
                case 'Dark':
                    return '';
                    break;
                case 'Poison':
                    return '';
                    break;
                case 'Electric':
                    return '';
                    break;
                case 'Psychic':
                    return '';
                    break;
                case 'Ground':
                    return '';
                    break;
                case 'Ice':
                    return '';
                    break;
                case 'Steel':
                    return '';
                    break;
                case 'Fairy':
                    return '';
                    break;
                case 'Fighting':
                    return '';
                    break;
                case 'Rock':
                    return '';
                    break;
            }
        },
        pokemonTypeBg(type1){
            switch(type1){
                case 'Grass':
                    return 'greenBg';
                    break;
                case 'Fire':
                    return 'redBg';
                    break;
                case 'Water':
                    return 'blueBg';
                    break;
                case 'Bug':
                    return '';
                    break;
                case 'Normal':
                    return '';
                    break;
                case 'Flying':
                    return '';
                    break;
                case 'Dark':
                    return '';
                    break;
                case 'Poison':
                    return '';
                    break;
                case 'Electric':
                    return '';
                    break;
                case 'Psychic':
                    return '';
                    break;
                case 'Ground':
                    return '';
                    break;
                case 'Ice':
                    return '';
                    break;
                case 'Steel':
                    return '';
                    break;
                case 'Fairy':
                    return '';
                    break;
                case 'Fighting':
                    return '';
                    break;
                case 'Rock':
                    return '';
                    break;
            }
        }
    }
}
</script>
<template lang="">
    <div>
        <div class="pokeCard" :class="pokemonType(pokemon.type1)">
            <div class="img" :class="pokemonTypeBg(pokemon.type1)">
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
    .red{
        background-color: rgb(253, 223, 223);
    }
    .green{
        background-color: rgb(222, 253, 224);
    }
    .blue{
        background-color: rgb(222, 243, 253);
    }
    .redBg{
        background-color: rgb(254, 237, 237);
    }
    .greenBg{
        background-color: rgb(235, 255, 237);
    }
    .blueBg{
        background-color: rgb(236, 247, 253);
    }
</style>