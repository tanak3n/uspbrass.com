<template>
  <div>
    <div class="top-background white--text with-shadow">
      <v-container class="pa-6">
        <v-row>
          <v-col>
            <h1 class="text-h3 mb-4">
              University of Shiga Prefecture Wind Orchestra
            </h1>
            <p class="subtitle-1">
              こんにちは！滋賀県立大学吹奏楽部です！コンクール、定期演奏会や依頼演奏に向けて日々練習に取り組んでいます！
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
      </v-container>
    </div>
    <v-container pt-6>
      <h2 class="text-center text-h3 py-5">お知らせ</h2>
      <v-card class="mx-auto my-5" elevation="2">
        <v-card-text>
          <p class="display-1 text--primary">
            12/6（日）に定期演奏会を開催します。
          </p>
          <div class="text--primary">
            <p>
              滋賀県立大学吹奏楽部は12/6（日）に定期演奏会を開催いたします。
              場所はひこね市文化プラザ、開場は13:00、開演は13:30となっております。皆様のご来場を心からお待ちしております。
            </p>
            <p>
              なお、今回の定期演奏会は新型コロナウイルス対策のため、来場された方の連絡先を控えさせていただきます。
              また、受付の混雑回避のため、ご来場の事前申し込みフォームを用意しております。ご協力をよろしくお願いいたします。ご不明な点がございましたら、ページ下部のお問い合わせボタンよりお気軽にお問い合わせください。
            </p>
          </div>
        </v-card-text>
        <v-card-actions>
          <v-btn
            text
            color="deep-purple accent-4"
            href="https://docs.google.com/forms/d/e/1FAIpQLSe4uNIkRrUMie7fwD_wrqEI0J2eolK7IaqLiRu6x9FrfPKMMw/viewform"
          >
            事前申し込みフォームはこちら
          </v-btn>
        </v-card-actions>
      </v-card>
      <v-card class="mx-auto my-5" style="height: 100%;" elevation="2">
        <v-card-text>
          <p class="display-1 text--primary">
            新入部員募集中！
          </p>
          <div class="text--primary">
            <p>
              滋賀県立大学吹奏楽部は新入部員を絶賛募集中です。
            </p>
          </div>
        </v-card-text>
      </v-card>
      <v-row>
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
              style="border: 0;"
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
          description: '滋賀県立大学 環境科学部棟 B8講義室 2F（圃場実験施設）',
        },
        {
          icon: 'mdi-clock-outline',
          term: '練習日時',
          description: '火・木 18:00—20:00、土 10:00—16:00',
        },
        {
          icon: 'mdi-account-group',
          term: '活動人数',
          description:
            '60人（B1: 15人、B2: 10人、B3: 15人、B4: 18人、M1: 2人）',
        },
      ],
    }
  },
  head() {
    return {
      title: this.title,
    }
  },
}
</script>

<style>
.with-shadow {
  text-shadow: black 1px 1px 10px, black -1px -1px 10px;
}
.top-background {
  background: 80% 80% url('~assets/regular_concert.jpg');
  background-size: cover;
}
</style>
