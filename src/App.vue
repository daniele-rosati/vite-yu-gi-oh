<script>
import axios from 'axios';
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue';

export default {
  components: {
    AppHeader
  },
  data() {
    return {
      store
    };
  }
}
</script>

<template>
  <AppHeader></AppHeader>
</template>

<style lang="scss" scoped>
      @use './style/general.scss';
</style>
