<template>
  <v-app>
    <v-app-bar fixed app>
      <v-avatar tile class="mr-2">
        <v-img src="/logo.png" />
      </v-avatar>
      <v-toolbar-title>滋賀県立大学吹奏楽部</v-toolbar-title>
      <v-btn text nuxt to="/" class="ml-5 hidden-xs-only">ホーム</v-btn>
      <v-spacer />
      <v-btn text nuxt to="/contact" class="hidden-xs-only">お問い合わせ</v-btn>
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer dark padless>
      <v-card flat tile class="text-center flex">
        <v-card-text class="headline font-weight-light">
          University of Shiga Prefecture Wind Orchestra
        </v-card-text>
        <v-btn outlined nuxt to="/contact">お問い合わせ</v-btn>
        <v-card-text class="mt-5">
          <v-btn
            v-for="footerIcon in footerIcons"
            :key="footerIcon.url"
            :href="footerIcon.url"
            class="mx-4 black--text"
            color="white"
            fab
          >
            <v-icon>{{ footerIcon.icon }}</v-icon>
          </v-btn>
        </v-card-text>
        <v-divider />
        <v-card-text>
          &copy; {{ new Date().getFullYear() }} University of Shiga Prefecture
          Wind Orchestra.
        </v-card-text>
      </v-card>
    </v-footer>
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
      title: '滋賀県立大学吹奏楽部',
      footerIcons: [
        { icon: 'mdi-twitter', url: 'https://twitter.com/uspbrass' },
        { icon: 'mdi-instagram', url: 'https://www.instagram.com/usp_brass/' },
        {
          icon: 'mdi-youtube',
          url: 'https://www.youtube.com/channel/UCVaybU4j_-bD7p8R3EA-k6w/'
        }
      ]
    }
  }
}
</script>
