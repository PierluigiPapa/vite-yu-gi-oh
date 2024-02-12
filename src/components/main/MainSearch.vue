<script>
import axios from "axios";
import {store} from "../../store.js"

export default {
    name: 'MainSearch',
    data() {
        return {
            store,
        };
    },
    methods: {
        getArchetype() {

            axios.get(store.apiUrlArchetype)
            .then(res => {
                
                store.arrayArchetype = res.data
            })
        }
    },
    mounted () {
        this.getArchetype()
    } 
}
</script>

<template>

<select v-model="store.selectValue" name=""  id="">
    <option 
    :value="element.archetype_name"
    v-for="(element, index) in store.arrayArchetype"
    :key="index">{{ element.archetype_name }}</option>
</select>
    
</template>

<style lang="scss" scoped>

select {
    margin: 20px 15px;
    padding: 10px;
    width: 160px;
    border-radius: 10px;
}

</style>