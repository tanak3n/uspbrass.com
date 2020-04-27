<template>
  <v-app>
    <v-app-bar fixed app>
      <v-toolbar-title v-text="title" />
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      //   clipped: false,
      //   drawer: false,
      //   fixed: false,
      //   miniVariant: false,
      //   right: true,
      //   rightDrawer: false,
      title: '滋賀県立大学吹奏楽部'
    }
  }
}
</script>
