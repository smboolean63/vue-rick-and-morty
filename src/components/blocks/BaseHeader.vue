<template>
  <header>
      <div class="container">
        <h1>Rick and Morty app</h1>
        <h2 v-if="search.searchText">Stai cercando per: {{search.searchText}}</h2>
      </div>
  </header>
</template>

<script>
import search from '../../shared/search';

export default {
  name: 'BaseHeader',
  data() {
    return {
      search
    }
  }
}
</script>

<style lang="scss" scoped>
header {
    padding: 1.875rem 0;
}
</style>