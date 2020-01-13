<template>
  <div id="app">
    <h1>Images Beyond Your Wildest Dreams</h1>
    <Search v-on:new-search="grabSearch"/>
    <Images v-bind:images="images" />
  </div>
</template>

<script>
import Images from './components/Images.vue';
import Search from './components/Search.vue';

export default {
  name: 'app',
  components: {
    Images,
    Search
  },
  data() {
    return {
      images: []
    }
  },
  methods: {
    grabSearch(newSearch) {
      this.search = newSearch
    }
  },
  created() {
    fetch('https://api.unsplash.com/search/photos?client_id=ACCESS_KEY&query=office')
      .then(res => this.images = res.data)
      .catch(err => console.log(err))
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
