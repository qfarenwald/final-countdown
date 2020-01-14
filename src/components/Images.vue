<template>
  <div>
    <div v-bind:key="image.id" v-for="image in images">
      <ImageItem v-bind:image="image" />
    </div>
  </div>
</template>

<script>
import ImageItem from './ImageItem.vue';

export default {
  name: "Images",
  components: {
    ImageItem
  },
  props: ["images"]
}
</script>

<style scoped>
  div {
    align-items: center;
    background-color: black;
    display: flex;
  }
</style>
