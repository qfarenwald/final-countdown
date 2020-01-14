<template>
  <div>
    <form @submit="grabSearch">
      <input type="text" v-model="search" name="search" placeholder="Image Description" id="inpt" />
      <input type="submit" value="SEARCH" id="btn" />
    </form>
  </div>
</template>

<script>
export default {
  name: "Search",
  data() {
    return {
      search: ''
    }
  },
  methods: {
    grabSearch(e) {
      e.preventDefault()
      const newSearch = this.search
      this.$emit('new-search', newSearch)
      this.search = '';
    }
  }
}
</script>

<style scoped>
  #inpt {
    border: none;
    padding: 10px 20px;
    width: 300px;
  }

  #btn {
    background-color: purple;
    border: none;
    color: white;
    padding: 10px 20px;
  }
</style>
