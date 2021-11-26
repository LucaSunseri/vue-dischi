<template>
  <div class="ls-card">

    <img :src="card.poster" :alt="card.title">

    <div class="ls-card__text">
      <h3>{{card.title}}</h3>
      <p>
        {{card.author}} <br>
        {{card.year}}
      </p>
    </div>
    
  </div>
</template>

<script>


export default {
  name: 'Card',
  props: {
    card: Object,
  }
}

</script>

<style lang="scss" scoped>
@import "../assets/style/vars.scss";

.ls-card {
  height: 100%;
  background-color: lighten($primary-color, 10%);
  padding: 20px;
  img {
    width: 100%;
  }
}

.ls-card__text {
  text-align: center;
  h3 {
    font-weight: bolder;
    margin: 20px 0;
  }
  p {
    color: gray;
    font-weight: bold;
  }
}

</style>