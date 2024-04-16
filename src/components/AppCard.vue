<script>
export default {
    name: 'CardCard',
    props: {
        cardInfo: Object
    }
}
</script>

<template>
    <div class="ms-card col-6 col-md-4 col-lg-3 col-xl-2">
        <div class="img-container">
            <img :src="cardInfo.card_images[0].image_url_small" :alt="cardInfo.name">
        </div>
        <div class="text-container d-flex flex-column align-items-center">
            <div class="name">{{ cardInfo.name }}</div>
            <div>{{ cardInfo.race }}</div>
        </div>
    </div>
</template>

<style scoped lang="scss">
@use '../style/partials/variables' as *;

.ms-card {
    .img-container {
        img {
            width: 100%;
        }
    }

    .text-container {
        height: 15%;
        background-color: $brand-primary;

        .name {
            font-size: .875rem;
        }
    }
}
</style>