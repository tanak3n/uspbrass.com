<template>
  <div>
    <v-parallax src="/parallax_regular_concert.jpg">
      <v-row>
        <v-col cols="12">
          <span class="display-1">滋賀県立大学吹奏楽部</span>
        </v-col>
      </v-row>
    </v-parallax>
    これはトップページの内容
  </div>
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
