<template>
  <div class="character">
      <img :src="character.image" :alt="character.name">
      <h5>{{character.name}}</h5>
      <hr>
      <div>{{character.origin}}</div>
      <div><strong>{{character.species}}</strong></div>
  </div>
</template>

<script>
export default {
    name: 'CardCharacter',
    props: {
        character: Object,
    }
}
</script>

<style lang="scss" scoped>
.character {
    text-align: center;
    img {
        max-width: 100%;
        border-radius: 50%;
        box-shadow: 2px 2px 10px #888;
        margin-bottom: 20px;
    }
    hr {
        max-width: 50px;
        margin: 1rem auto;
        opacity: 1;
    }
}
</style>