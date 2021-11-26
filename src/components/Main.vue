<template>
  <main>
    <div class="container">
      <div class="row row-cols-2 row-cols-md-3 row-cols-lg-5">
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
      </div>
    </div>    
  </main>
</template>

<script>
import Card from "./Card.vue"

export default {
  name: 'Main',
  components: {
    Card,
  }
}
</script>

<style lang="scss" scoped>
@import "../assets/style/vars.scss";

main {
  height: calc(100vh - 70px);
  background-color: $primary-color;
  overflow: auto;
}

</style>