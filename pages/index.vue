<template>
  <v-container fluid>
    <v-img max-height="450px" position="50% 90%" src="/regular_concert.jpg">
      <v-row
        align="center"
        justify="center"
        class="lightbox white--text pa-2 fill-height"
      >
        <v-col class="text-center" cols="12">
          <h1 class="display-1 mb-4">
            University of Shiga Prefecture Wind Orchestra
          </h1>
        </v-col>
      </v-row>
    </v-img>
    <!-- これはトップページの内容 -->
    <div style="height: 5000px;"></div>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      title: 'ホーム'
    }
  },
  head() {
    return {
      title: this.title
    }
  }
}
</script>
