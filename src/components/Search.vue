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
    grabSearch() {
      
    }
  }
}
</script>

<style scoped>

</style>
