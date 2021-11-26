<template>
  <div class="d-flex justify-content-center align-items-center ls-loading">
    <strong>Loading...</strong>
    <b-spinner variant="primary" class="ml-auto mx-2"></b-spinner>
  </div>

</template>

<script>
export default {
  name: 'Spinner'

}
</script>

<style lang="scss" scoped>

.ls-loading {
  margin-top: 150px;
}

</style>