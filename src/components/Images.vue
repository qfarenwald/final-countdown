<template>
  <div>
    <div v-bind:key="image.id" v-for="image in images">
      <h3>{{ image.image }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "Images",
  props: ["images"]
}

</script>

<style scoped>

</style>
