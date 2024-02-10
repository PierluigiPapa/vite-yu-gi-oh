<script>
export default {
    name: 'Header',
}

</script>

<template>
    <header>
        <div class="header-container">
           <img class="yugi-logo" src="/img/logo.png" alt="">
           <h1>Yu-Gi-Oh Api</h1>
        </div>
    </header>
        
   
    
</template>

<style lang="scss" scoped>
@use '../../styles/partials/variables.scss' as *;

.header-container {
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 20px;
    padding: 15px;

    .yugi-logo {
        width: 80px;
    }

    h1 {
        font-size: 35px;
        font-weight: normal;
    }
}

    
</style>