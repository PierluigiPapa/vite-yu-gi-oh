<script>
import MainSearch from './MainSearch.vue';
import MainCards from './MainCards.vue';

import { store } from '@/store';
import axios from 'axios';


export default {
    name: 'Main',
    components: {
        MainSearch,
        MainCards,
    },
    methods: {
        ricerca() {
            if(store.selectValue !=="") {
                axios
            .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&archetype=" + store.selectValue).then (response => {
                console.log(response.data)
                store.yugiCards = response.data.data
            }) 
            }else{
                axios
            .get(store.apiUrl).then (response => {
                console.log(response.data)
                store.yugiCards = response.data.data
            })
            }
        }
    },
    mounted () {
        this.ricerca()
    }
}
</script>

<template>
    <main>
        <div class="main-container">
            <MainSearch @ricerca="ricerca"/>
            
            <MainCards></MainCards>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use '../../styles/partials/variables.scss' as *;

main {
    background-color: $bg-main;

    .main-container {
        max-width: 100%;
        margin: 0 auto;
    }
}
</style>