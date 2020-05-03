<template>
  <div>
    <v-container fluid>
      <v-alert type="info">
        現在、新型コロナウイルスの影響で活動を自粛しています。
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
              こんにちは！滋賀県立大学吹奏楽部です！コンクールや定期演奏会，依頼演奏に向けて日々練習に取り組んでいます！
            </p>
            <v-divider dark />
            <dl>
              <dt class="font-weight-black mt-4">
                <v-icon color="white" class="mr-1">mdi-map-marker</v-icon
                >練習場所
              </dt>
              <dd>
                滋賀県立大学 環境科学部B8棟 <ruby>圃場<rt>ほじょう</rt></ruby>
              </dd>
              <dt class="font-weight-black mt-4">
                <v-icon color="white" class="mr-1">mdi-clock-outline</v-icon
                >練習日時
              </dt>
              <dd>火・木 18:00—20:00，土 10:00—16:00</dd>
              <dt class="font-weight-black mt-4">
                <v-icon color="white" class="mr-1">mdi-account-group</v-icon
                >活動人数
              </dt>
              <dd>48人（1回生: 1人，2回生: 10人，3回生: 14人，4回生: 18人）</dd>
            </dl>
          </v-col>
        </v-row>
      </v-img>
      <!-- これはトップページの内容 -->
    </v-container>
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

<style>
.with-shadow {
  text-shadow: black 1px 1px 10px, black -1px -1px 10px;
}
</style>
