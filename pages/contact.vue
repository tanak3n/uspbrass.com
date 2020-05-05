<template>
  <v-container>
    <h1>{{ title }}</h1>
    <v-row>
      <v-col sm="4" cols="12" align-self="stretch"
        ><v-card tile height="100%" color="#1DA1F2" dark>
          <v-card-title
            ><v-icon large left>mdi-twitter</v-icon
            ><span class="title font-weight-light">Twitter</span> </v-card-title
          ><v-card-text class="white--text"
            >吹奏楽部公式Twitterです。Twitterアカウントをお持ちの方はこちらからお問い合わせください。</v-card-text
          ><v-card-actions>
            <v-btn
              color="white"
              light
              class="mx-auto"
              href="https://twitter.com/messages/compose?recipient_id=1501306436"
              >お問い合わせ（DM）</v-btn
            >
          </v-card-actions></v-card
        ></v-col
      >
      <v-col sm="4" cols="12" align-self="stretch"
        ><v-card tile height="100%" color="purple" dark>
          <v-card-title
            ><v-icon large left>mdi-comment-question</v-icon
            ><span class="title font-weight-light"
              >お問い合わせフォーム</span
            > </v-card-title
          ><v-card-text class="white--text"
            >Twitterアカウントをお持ちでない方は、こちらのフォームからお問い合わせください。</v-card-text
          ><v-card-actions>
            <v-btn color="white" light class="mx-auto">フォームを開く</v-btn>
          </v-card-actions></v-card
        ></v-col
      >
      <v-col sm="4" cols="12" align-self="stretch"
        ><v-card tile height="100%" color="secondary" dark>
          <v-card-title
            ><v-icon large left>mdi-email</v-icon
            ><span class="title font-weight-light">メール</span> </v-card-title
          ><v-card-text class="white--text"
            >メールでの問い合わせも受け付けております。メールアドレスは
            <code>uspbrass@yahoo.co.jp</code> です。</v-card-text
          ><v-card-actions>
            <v-btn
              color="white"
              light
              class="mx-auto"
              href="mailto:uspbrass@yahoo.co.jp"
              >お問い合わせ（メール）</v-btn
            >
          </v-card-actions></v-card
        ></v-col
      >
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      title: 'お問い合わせ'
    }
  },
  head() {
    return {
      title: this.title
    }
  }
}
</script>
