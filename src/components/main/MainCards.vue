<script>
import NumberCards from "./NumberCards.vue";
import Cards from "./Cards.vue";

import {store} from "../../store.js"
import axios from "axios";

export default {
    name: 'MainCards',
    components: {
        NumberCards,
        Cards,
    },
    data () {
        return {
            store
        }
    }, 
    methods: {
        getYugi() {

            store.loading = true


            axios.get(store.apiUrl)
            .then(res => {
                
                store.yugiCards = res.data.data

                store.loading = false
            })
        }
    },
    mounted () {
        this.getYugi()
    } 
}
</script>

<template>
    <div class="container-cards">
        <NumberCards></NumberCards>

        <ul class="list-cards">
            <li v-for="card in store.yugiCards">
                <Cards
                :img="card.card_images[0].image_url"
                :name="card.name"
                :type="card.archetype"/>
            </li>
        </ul>
    </div>
</template>

<style lang="scss" scoped>
@use '../../styles/partials/variables.scss' as *;

.container-cards {
    padding: 50px;
    background-color: white;

    .list-cards {
        display: flex;
        flex-direction: row;
        gap: 25px;
        flex-wrap: wrap;
        text-align: center;
    }

    li {
        width: calc((100% / 5 - 20px));
        background-color: $bg-main;
        list-style-type: none;
        aspect-ratio: 3/4;
    }
}
</style>