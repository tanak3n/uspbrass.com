<template>
  <v-container>
    <h1>{{ title }}</h1>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      title: '大会記録'
    }
  },
  head() {
    return {
      title: this.title
    }
  }
}
</script>
