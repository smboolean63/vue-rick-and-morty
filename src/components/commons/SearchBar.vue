<template>
  <div>
      <form class="d-flex gap-3" @submit.prevent="$emit('searching', searchText)">
          <input type="text" class="form-control" placeholder="Search character" v-model="search.searchText">
          <button type="submit" class="btn btn-primary">Search</button>
          <button type="button" class="btn btn-warning">Reset</button>
      </form>
  </div>
</template>

<script>
import search from '../../shared/search.js';

export default {
    name: 'SearchBar',
    data() {
        return {
            search
        };
    },
}
</script>

<style lang="scss" scoped>

</style>