<template>
  <div>
    <img v-bind:src="image.urls.full">
  </div>
</template>

<script>
export default {
  name: 'ImageItem',
  props: ["image"]
}
</script>

<style scoped>
  img {
    width: 100%;
  }
</style>
