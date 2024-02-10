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
        </div>
    </div>

    <div class="card-name"> <h4>{{ name }}</h4></div>
    <div class="card-type"> <span>{{ type }}</span></div>
</template>

<style lang="scss" scoped>

.card {
    display: flex;
    flex-direction: column;
    gap: 25px;

    .card-name {
        font-weight: bold;
        text-transform: uppercase;

        h4 {
            color: white;
            text-align: center;
        }
    }
    .card-type {
        margin-bottom: 5px;

        span {
            color: black;
            text-align: center;
        }
    }
    
}
</style>