<script>
import axios from 'axios';
import { store } from '../store.js';

export default {
    name: 'AppFilter',
    data() {
        return {
            store
        };
    },
    methods: {
        getArchetypesfromApi() {
            axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
            .then((response) => {
                store.archetypes = response.data;
                store.archetypes.unshift({
                    archetype_name: 'Archetype',
                });
                store.filterArchetype = store.archetypes[0].archetype_name;
            })
        }
    },
    mounted() {
        this.getArchetypesfromApi();
    }
}
</script>

<template>
    <div class="container py-5">
        <select name="archetypes" @change="$emit('filter')" v-model="store.filterArchetype">
            <option v-for="archetype in store.archetypes" :value="archetype.archetype_name">{{ archetype.archetype_name }}</option>
        </select>
    </div>
</template>

<style scoped lang="scss"></style>