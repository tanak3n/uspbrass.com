<template>
  <v-container>
    <h1>{{ title }}</h1>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      title: '当部について'
    }
  },
  head() {
    return {
      title: this.title
    }
  }
}
</script>
