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
      <!-- これはトップページの内容 -->
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
