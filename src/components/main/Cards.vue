<script>
export default {
    name: 'Cards',
    props: {
        img: String,
        name: String,
        type: String,
    },
}
</script>

<template>
    <div class="card">
        <div class="card-image">
            <img :src="img" :alt="name">

            <div class="card-name"> {{ name }}</div>
            <div class="card-type"> {{ type }}</div>
        </div>
    </div>

    
</template>

<style lang="scss" scoped>

.card {
    display: flex;
    flex-direction: column;
    gap: 25px;
    width: 100%;

    .card-image {
        width: 100%;
        img {
            width: 100%;
        }
    }

    .card-name {
        font-weight: bold;
        text-transform: uppercase;
        color: white;
        padding-bottom: 20px;
    }
    .card-type {
        margin-bottom: 5px;
    }
    
}
</style>