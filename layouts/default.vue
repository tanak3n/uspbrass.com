<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" app>
      <v-list dense nav>
        <v-list-item
          v-for="naviItem in naviItems"
          :key="naviItem.title"
          link
          nuxt
          :to="naviItem.to"
        >
          <v-list-item-icon>
            <v-icon>{{ naviItem.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ naviItem.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-avatar tile class="mr-2">
        <v-img :src="require('~/assets/logo.png')" />
      </v-avatar>
      <v-toolbar-title>滋賀県立大学吹奏楽部</v-toolbar-title>
      <v-btn text nuxt to="/" class="ml-5 hidden-xs-only">ホーム</v-btn>
      <v-spacer />
      <v-btn text nuxt to="/contact" class="hidden-xs-only">お問い合わせ</v-btn>
    </v-app-bar>
    <v-content>
      <nuxt />
    </v-content>
    <v-footer dark padless app absolute>
      <v-card flat tile class="text-center flex">
        <v-card-text class="headline font-weight-light">
          University of Shiga Prefecture Wind Orchestra
        </v-card-text>
        <v-btn outlined nuxt to="/contact">お問い合わせ</v-btn>
        <v-card-text class="mt-5">
          <v-btn
            v-for="(footerItem, i) in footerItems"
            :key="i"
            :href="footerItem.href"
            class="mx-4 black--text"
            color="white"
            fab
          >
            <v-icon>{{ footerItem.icon }}</v-icon>
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
      drawer: null,
      //   fixed: false,
      //   miniVariant: false,
      //   right: true,
      //   rightDrawer: false,
      title: '滋賀県立大学吹奏楽部',
      footerItems: [
        { icon: 'mdi-twitter', href: 'https://twitter.com/uspbrass' },
        { icon: 'mdi-instagram', href: 'https://www.instagram.com/usp_brass/' },
        {
          icon: 'mdi-youtube',
          href: 'https://www.youtube.com/channel/UCVaybU4j_-bD7p8R3EA-k6w/'
        }
      ],
      naviItems: [
        { title: 'ホーム', icon: 'mdi-home', to: '/' },
        // { title: '当部について', icon: 'mdi-information', to: '/about' },
        { title: '大会記録', icon: 'mdi-history', to: '/records' },
        { title: 'お問い合わせ', icon: 'mdi-help-circle', to: '/contact' }
      ]
    }
  }
}
</script>
