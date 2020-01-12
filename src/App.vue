<template>
  <div id="app">
    {{ msg }}
  </div>
</template>

<script>

export default {
  name: 'app',
  components: {

  },
  data() {
    return {
      images: [
        {
          id: 1,
          image: "image 1"
        },
        {
          id: 2,
          image: "image 2"
        }
      ]
    }
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
</style>
