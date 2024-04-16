<script>
export default {
    name: 'AppHeader'
}
</script>

<template>
    <header>
        <nav class="navbar">
            <div class="container-fluid justify-content-start fs-5">
                <a class="navbar-brand" href="#">
                    <img src="../assets/img/yu-gi-oh-logo.svg" alt="Yu-Gi-Oh!" width="200px">
                </a>
                Yu-Gi-Oh! Api
            </div>
        </nav>
    </header>
</template>

<style scoped lang="scss">
@use '../style/partials/variables' as *;

header {
    background-color: $brand-light;
}
</style>