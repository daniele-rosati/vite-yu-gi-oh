<script>
import axios from 'axios';
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue';
import AppFilter from './components/AppFilter.vue';
import AppLoader from './components/AppLoader.vue';
import AppCardsList from './components/AppCardList.vue';

export default {
  components: {
    AppHeader,
    AppFilter,
    AppLoader,
    AppCardsList
  },
  data() {
    return {
      store,
      queryParams: {
        num: 24,
        offset: 0
      }
    };
  },
  methods: {
    getCardFromApi() {
      let apiUrl = 'https://db.ygoprodeck.com/api/v7/cardinfo.php';
      // Archetype filter
      if (store.filterArchetype === 'Archetype') {
        this.queryParams.archetype = undefined;
      } else {
        this.queryParams.archetype = store.filterArchetype;
      }
      axios.get(apiUrl, {
        params: this.queryParams
      })
      .then((response) => {
        store.cards = response.data.data;
        store.isLoading = false;
      });
    },
  },
  mounted() {
    this.getCardFromApi();
  }
}
</script>

<template>
  <AppHeader></AppHeader>
  <main>
    <AppFilter @filter="getCardFromApi"></AppFilter>
    <AppLoader v-if="store.isLoading"></AppLoader>
    <AppCardsList v-else></AppCardsList>
  </main>
</template>

<style lang="scss">
@use './style/general.scss';
@use './style/partials/_variables' as *;

body {
    background-color: $brand-primary;
}
</style>