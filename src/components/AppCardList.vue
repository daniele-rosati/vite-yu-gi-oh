<script>
import AppCard from './AppCard.vue';
import { store } from '../store';

export default {
    name: 'CardsList',
    components: {
        AppCard
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
        <div class="container pb-5">
            <div class="row row-cols-2 row-cols-md-3 row-cols-lg-4 row-cols-xl-6 justify-content-center pb-3 g-3">
                <AppCard v-for="card in store.cards" :key="card.id" :cardInfo="card"></AppCard>
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