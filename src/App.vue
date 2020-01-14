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
      images: null,
      search: 'dog'
    }
  },
  methods: {
    grabSearch(newSearch) {
      this.search = newSearch
    },
    fetchItems(search) {
      const url = `https://api.unsplash.com/search/photos?client_id=e74d7defe8b9af62352bfd945a1d035336288951f2ecc967113f84643977f840&query=${search}`;
       fetch(url)
         .then(res => res.json())
         .then(data => this.images = data.results)
         .catch(error => console.error(error))
     }
  },
  mounted() {
    this.fetchItems(this.search)
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
