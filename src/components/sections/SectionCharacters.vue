<template>
  <section>
      <div class="container">
          <div class="row mb-5">
              <div class="col-12">
                  <SearchBar @searching="filterCharacters"/>
              </div>
          </div>
          <div class="row">
            <CardCharacter class="col-12 col-sm-6 col-lg-3 mb-3" v-for="character in charactersFiltered" :key="character.id" :character="character"/>
          </div>
      </div>
  </section>
</template>

<script>
import axios from 'axios';
import CardCharacter from '../commons/CardCharacter.vue';
import SearchBar from '../commons/SearchBar.vue';

import search from '../../shared/search.js';

export default {
    name: 'SectionCharacters',
    data() {
        return {
            search,
            characters: [],
        };
    },
    components: {
        CardCharacter,
        SearchBar,
    },
    created() {
        axios.get('https://api.sampleapis.com/rickandmorty/characters')
        .then((response) => {
            // handle success
            this.characters = response.data;
            // this.charactersFiltered = response.data;
        })
        .catch((error) => {
            // handle error
            console.log(error);
        });
    },
    methods: {
        filterCharacters(searchText) {
            this.searchText = searchText;
            // this.charactersFiltered = this.characters.filter((elm) => { 
            //     console.log('ciao');
            //     return elm.name.toLowerCase().includes(searchText.toLowerCase());
            // });
        }
    },
    computed: {
        charactersFiltered() {
            return this.characters.filter((elm) => { 
                return elm.name.toLowerCase().includes(this.search.searchText.toLowerCase());
            });
        }
    }
}
</script>

<style lang="scss" scoped>

</style>