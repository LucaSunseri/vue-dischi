<template>
  <main>
    <div class="container">

      <div class="row row-cols-2 row-cols-md-3 row-cols-lg-5">
        <div v-for="(card, index) in cards" :key="index" class="col mb-5">
          <Card :card="card" />
        </div>
      </div>

    </div>    
  </main>
</template>

<script>
import axios from 'axios';

import Card from "./Card.vue"

export default {
  name: 'Main',
  components: {
    Card,
  },
  data() {
    return {
      cards: [],
      apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music'
    }
  },
  mounted() {
    this.getApi();
  },
  methods: {
    getApi() {
      axios.get(this.apiUrl)
      .then(response => {
        this.cards = response.data.response;
        console.log('carte', this.cards);
      })
      .catch(error => {
        console.log(error);
      })
    }
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