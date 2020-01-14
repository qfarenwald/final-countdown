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
import dotenv from 'dotenv';

dotenv.config()

export default {
  name: 'app',
  components: {
    Images,
    Search
  },
  data() {
    return {
      images: [],
      search: ''
    }
  },
  methods: {
    grabSearch(newSearch) {
      this.search = newSearch
    }
  },
  created() {
    console.log('key', process.env.VUE_APP_ACCESS_KEY)
    fetch(`https://api.unsplash.com/search/photos?client_id=${process.env.VUE_APP_ACCESS_KEY}&query=dog`)
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
