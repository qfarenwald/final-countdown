<template>
  <div>
    <form @submit="grabSearch">
      <input type="text" v-model="search" name="search" placeholder="Image Description" />
      <input type="submit" value="Submit" class="btn" />
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
      const newSearch = {
        id: Date.now(),
        search: this.search
      }
      this.$emit('new-search', newSearch)
      this.search = '';
    }
  }
}
</script>

<style scoped>

</style>
