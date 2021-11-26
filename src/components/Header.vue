<template>
  <header>
    <div class="header__left">
      <img src="../assets/img/logo.svg" alt="Logo">
    </div>   
    <div class="header__right">
      //TODO LUNEDI
    </div>   
  </header>
</template>

<script>
export default {
  name: 'Header',

}
</script>

<style lang="scss" scoped>
@import "../assets/style/vars.scss";

header {
  height: 70px;
  display: flex;
  justify-content: space-between;
  background-color: lighten($primary-color, 10%);
}

.header__left {
  display: flex;
  align-items: center;
  margin-left: 10px;
    img {
    width: 100%;
    height: 100%;
    padding: 10px;
  }
}

</style>