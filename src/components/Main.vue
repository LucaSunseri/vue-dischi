<template>
  <main>
    <div class="container">

      <Select @filteredGenres="performSearch" class="mb-4"/>

      <div v-if="loading" class="row row-cols-2 row-cols-md-3 row-cols-lg-4 row-cols-xl-5">
        <div v-for="(card, index) in filteredGenres" :key="index" class="col mb-5">
          <Card :card="card" />
        </div>
      </div>

      <div v-else class="row">
        <div class="col ">
          <Spinner />
        </div>
      </div>


    </div>    
  </main>
</template>

<script>
import axios from 'axios';

import Card from "./Card.vue"
import Spinner from "./Spinner.vue"
import Select from "./Select.vue"

export default {
  name: 'Main',
  components: {
    Card,
    Spinner,
    Select
  },
  data() {
    return {
      cards: [],
      loading: false,
      apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
      genres: null,
    }
  },
    computed:{
    filteredGenres(){
      if(this.genres === null){
        return this.cards;
      }
      const arrayFiltered = this.cards.filter( item => {
        return item.genre === this.genres;
      });
      return arrayFiltered;
    },
  },
  mounted() {
    this.getApi();
  },
  methods: {
    getApi() {
      axios.get(this.apiUrl)
      .then(response => {
        this.cards = response.data.response;
        this.loading = true;
      })
      .catch(error => {
        console.log(error);
      })
    },

     performSearch(text){
      this.genres = text;
      console.log(this.genres);
    },
  }
}
</script>

<style lang="scss" scoped>
@import "../assets/style/vars.scss";

main {
  height: calc(100vh - 70px);
  background-color: $primary-color;
  overflow: auto;
  padding: 50px 0;
}

</style>