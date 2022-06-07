<template>
  <section>
      <div class="container">
          <div class="row">
            <CardCharacter class="col-12 col-sm-6 col-lg-3 mb-3" v-for="character in characters" :key="character.id" :character="character"/>
          </div>
      </div>
  </section>
</template>

<script>
import axios from 'axios';
import CardCharacter from '../commons/CardCharacter.vue';

export default {
    name: 'SectionCharacters',
    data() {
        return {
            characters: [],
        };
    },
    components: {
        CardCharacter,
    },
    created() {
        axios.get('https://api.sampleapis.com/rickandmorty/characters')
        .then((response) => {
            // handle success
            this.characters = response.data;
        })
        .catch((error) => {
            // handle error
            console.log(error);
        });
    }
}
</script>

<style lang="scss" scoped>

</style>