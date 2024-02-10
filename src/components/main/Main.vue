<script>
import MainSearch from './MainSearch.vue';
import MainCards from './MainCards.vue';


export default {
    name: 'Main',
    components: {
        MainSearch,
        MainCards,
    }
}
</script>

<template>
    <main>
        <div class="main-container">
            <MainSearch></MainSearch>
            
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