<template>
  <div>
    <!-- <p>{{ image.urls.full }}</p> -->
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

</style>
