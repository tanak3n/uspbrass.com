<template>
  <div>
    <v-container fluid>
      <v-alert type="info">
        現在、新型コロナウイルスの影響で活動を休止しています。
      </v-alert>
      <v-img max-height="500px" position="50% 90%" src="/regular_concert.jpg">
        <v-row
          align="center"
          justify="center"
          class="lightbox white--text pa-2 fill-height"
        >
          <v-col class="with-shadow" cols="12">
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
      <v-row>
        <v-col cols="12" md="6">
          <v-card>
            <v-card-title>ホームページをリニューアルしました</v-card-title>
            <v-card-text
              >5/5より吹奏楽部のホームページが新しくなりました。今後、演奏会の情報やパート紹介などのコンテンツを充実させていきます。これからもよろしくお願いいたします。</v-card-text
            >
          </v-card>
        </v-col>
        <v-col cols="12" md="6">
          <v-card>
            <v-card-title>新入部員募集中！</v-card-title>
            <v-card-text
              >滋賀県立大学吹奏楽部は新入部員を絶賛募集中です。</v-card-text
            >
          </v-card>
        </v-col>
        <v-col cols="12" md="4">
          <v-card>
            <v-btn class="float-right mt-4 mr-4">
              <v-icon>mdi-twitter</v-icon>
              Open Timeline
            </v-btn>
            <v-card-title>Twitter</v-card-title>
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
          <v-card>
            <v-card-title>アクセス</v-card-title>
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1628.9431528157104!2d136.21523965815865!3d35.259084185232744!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zMzXCsDE1JzMyLjciTiAxMzbCsDEyJzU4LjgiRQ!5e0!3m2!1sja!2sjp!4v1554401176613!5m2!1sja!2sjp"
              width="100%"
              height="500"
              frameborder="0"
              style="border:0"
              allowfullscreen
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
