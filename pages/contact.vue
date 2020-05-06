<template>
  <v-container>
    <h1>{{ title }}</h1>
    <v-row class="text-center" justify="center">
      <v-col md="4" sm="6" cols="12" align-self="stretch"
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
      <v-col md="4" sm="6" cols="12" align-self="stretch"
        ><v-card tile height="100%" color="purple" dark>
          <v-card-title
            ><v-icon large left>mdi-comment-question</v-icon
            ><span class="title font-weight-light"
              >お問い合わせフォーム</span
            > </v-card-title
          ><v-card-text class="white--text"
            >Twitterアカウントをお持ちでない方は、こちらのフォームからお問い合わせください。</v-card-text
          ><v-card-actions>
            <v-btn
              color="white"
              light
              class="mx-auto"
              href="https://docs.google.com/forms/d/e/1FAIpQLSduGmIi2YGcIs9tl3gfCORbA30DDhwM2TrFow6r3K2kHvj2HQ/viewform?usp=sf_link"
              >フォームを開く</v-btn
            >
          </v-card-actions></v-card
        ></v-col
      >
      <v-col md="4" sm="6" cols="12" align-self="stretch"
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
    <h1>アクセス</h1>
    <v-row>
      <v-col md="5" cols="12">
        <v-card tile height="100%">
          <v-card-title>連絡先</v-card-title>
          <v-card-text class="text-center">
            〒522-0057<br />
            滋賀県彦根市八坂町2500 滋賀県立大学内<br />
            滋賀県立大学吹奏楽部
          </v-card-text>
        </v-card>
      </v-col>
      <v-col md="7" cols="12">
        <v-card tile height="100%"
          ><v-card-title>地図</v-card-title
          ><iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d814.4739490479199!2d136.21604282924622!3d35.25884809385076!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zMzXCsDE1JzMxLjkiTiAxMzbCsDEyJzU5LjciRQ!5e0!3m2!1sja!2sjp!4v1588748287601!5m2!1sja!2sjp"
            width="100%"
            height="450"
            frameborder="0"
            style="border:0;"
            allowfullscreen=""
            aria-hidden="false"
            tabindex="0"
          ></iframe
        ></v-card>
      </v-col>
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
