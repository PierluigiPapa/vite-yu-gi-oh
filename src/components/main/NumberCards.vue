<script>
import {store} from "../../store.js"


export default {
    name: 'NumberCards',
    data() {
        return {
            store,
        };
    },
}
</script>

<template>
    <div class="container-number-cards">
        <h3>Found {{ store.yugiCards.length }} cards</h3>
    </div>
</template>

<style lang="scss" scoped>

.container-number-cards {
    background-color: black;
    padding: 25px 15px;
    width: 100%;

    h3 {
        color: white;
    }
}
</style>