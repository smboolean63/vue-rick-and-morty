<template>
  <div id="app">
    <BaseHeader/>
  </div>
</template>

<script>
import BaseHeader from './components/blocks/BaseHeader.vue';

export default {
  name: 'App',
  components: {
    BaseHeader,
  }
}
</script>

<style lang="scss">
@import 'assets/style/global.scss';
</style>
