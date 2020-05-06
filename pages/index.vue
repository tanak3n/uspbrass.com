<template>
  <div>
    <v-container fluid class="ma-0 pa-0">
      <v-img height="100vh" position="50% 90%" src="/regular_concert.jpg">
        <v-row
          align="center"
          justify="center"
          class="white--text mx-3 fill-height text-center"
        >
          <v-col class="with-shadow my-1" cols="12">
            <h1 class="display-1 mb-4">
              University of Shiga Prefecture Wind Orchestra
            </h1>
            <p class="subtitle-1">
              こんにちは！滋賀県立大学吹奏楽部です！コンクール，定期演奏会や依頼演奏に向けて日々練習に取り組んでいます！
            </p>
            <v-divider dark />
            <dl v-for="(jumbotronItem, i) in jumbotronItems" :key="i">
              <dt class="font-weight-black mt-4">
                <v-icon color="white" class="mr-1">{{
                  jumbotronItem.icon
                }}</v-icon
                >{{ jumbotronItem.term }}
              </dt>
              <dd>
                {{ jumbotronItem.description }}
              </dd>
            </dl>
          </v-col>
        </v-row>
      </v-img>
    </v-container>
    <v-container>
      <v-alert type="info">
        現在、新型コロナウイルスの影響で活動を休止しています。
      </v-alert>
      <v-row>
        <v-col cols="12" md="6">
          <v-card class="pa-3" height="100%">
            <h2 class="headline font-weight-light">
              ホームページをリニューアルしました
            </h2>
            <p class="mt-4">
              5/5より吹奏楽部のホームページが新しくなりました。今後、演奏会の情報やパート紹介などのコンテンツを充実させていきます。これからもよろしくお願いいたします。
            </p>
          </v-card>
        </v-col>
        <v-col cols="12" md="6">
          <v-card class="pa-3" height="100%">
            <h2 class="headline font-weight-light">
              新入部員募集中！
            </h2>
            <p class="mt-4">
              滋賀県立大学吹奏楽部は新入部員を絶賛募集中です。
            </p>
          </v-card>
        </v-col>
        <v-col cols="12" md="4">
          <v-card class="pa-3">
            <h2 class="headline font-weight-light mb-4">
              Twitter
            </h2>
            <a
              class="twitter-timeline"
              data-height="500"
              href="https://twitter.com/uspbrass?ref_src=twsrc%5Etfw"
              data-chrome="nofooter noheader"
              >Tweets by uspbrass</a
            >
            <script
              async
              src="https://platform.twitter.com/widgets.js"
              charset="utf-8"
            ></script>
          </v-card>
        </v-col>
        <v-col cols="12" md="8">
          <v-card class="pa-3">
            <h2 class="headline font-weight-light mb-4">
              アクセス
            </h2>
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d814.4739490479199!2d136.21604282924622!3d35.25884809385076!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zMzXCsDE1JzMxLjkiTiAxMzbCsDEyJzU5LjciRQ!5e0!3m2!1sja!2sjp!4v1588748287601!5m2!1sja!2sjp"
              width="100%"
              height="500"
              frameborder="0"
              style="border:0;"
              allowfullscreen=""
              aria-hidden="false"
              tabindex="0"
            ></iframe>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'ホーム',
      jumbotronItems: [
        {
          icon: 'mdi-map-marker',
          term: '練習場所',
          description: '滋賀県立大学 環境科学部棟 B8講義室 2F（圃場実験施設）'
        },
        {
          icon: 'mdi-clock-outline',
          term: '練習日時',
          description: '火・木 18:00—20:00，土 10:00—16:00'
        },
        {
          icon: 'mdi-account-group',
          term: '活動人数',
          description:
            '48人（1回生: 1人，2回生: 10人，3回生: 14人，4回生: 18人）'
        }
      ]
    }
  },
  head() {
    return {
      title: this.title
    }
  }
}
</script>

<style>
.with-shadow {
  text-shadow: black 1px 1px 10px, black -1px -1px 10px;
}
</style>
