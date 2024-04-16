<script>
import CardCard from './CardCard.vue';
import { store } from '../store';

export default {
    name: 'CardsList',
    components: {
        CardCard
    },
    data() {
        return {
            store
        };
    }
}
</script>

<template>
    <section class="card-list">
        <div class="container py-5">
            <div class="row pb-3 g-3">
                <CardCard v-for="card in store.cards" :key="card.id" :cardInfo="card"></CardCard>
            </div>
        </div>
    </section>
</template>

<style scoped lang="scss">
@use '../style/partials/variables' as *;

.card-list {
    background-color: $brand-primary;

    .row {
        background-color: $brand-light;
    }
}
</style>