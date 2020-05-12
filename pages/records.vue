<template>
  <v-container>
    <v-row align="center" justify="center">
      <v-col sm="auto" cols="12">
        <h1 class="display-2 text-center">{{ title }}</h1>
      </v-col>
      <v-col md="5" sm="6" cols="10">
        <p>
          滋賀県立大学吹奏楽部は、毎年夏に行われる全日本吹奏楽連盟・朝日新聞主催の吹奏楽コンクール、冬に行われるアンサンブルコンテストに出場しています。
        </p>
      </v-col>
    </v-row>
    <h2 class="hidden-sm-and-up">吹奏楽コンクール</h2>
    <v-row class="hidden-sm-and-up">
      <v-col v-for="item in competitionRecords" :key="item.year" cols="12">
        <v-card>
          <v-card-title>{{ item.year }}年</v-card-title>
          <v-card-text>
            <dl>
              <dt class="font-weight-bold">課題曲</dt>
              <dd class="ml-2">{{ item.required ? item.required : '不明' }}</dd>
              <dt class="font-weight-bold">自由曲</dt>
              <dd class="ml-2">{{ item.free ? item.free : '不明' }}</dd>
              <dt class="font-weight-bold">指揮者</dt>
              <dd class="ml-2">
                {{ item.conductor ? item.conductor : '不明' }}
              </dd>
            </dl>
          </v-card-text>
          <v-card-title>県大会</v-card-title>
          <v-card-text>
            <v-avatar
              v-if="item.prefResult.prize === 'gold'"
              class="mx-2"
              color="#BFA95F"
            >
              <span class="black--text">金賞</span>
            </v-avatar>
            <v-avatar
              v-else-if="item.prefResult.prize === 'silver'"
              class="mx-2"
              color="grey"
            >
              <span class="white--text">銀賞</span>
            </v-avatar>
            <v-avatar
              v-else-if="item.prefResult.prize === 'bronze'"
              class="mx-2"
              color="brown"
            >
              <span class="white--text">銅賞</span>
            </v-avatar>
            <span v-else>不明</span>
            <span v-if="item.prefResult.representative">滋賀県代表</span>
          </v-card-text>
          <template v-if="item.prefResult.representative">
            <v-card-title>関西大会</v-card-title>
            <v-card-text>
              <v-avatar
                v-if="item.kansaiResult.prize === 'gold'"
                class="mx-2"
                color="#BFA95F"
              >
                <span class="black--text">金賞</span>
              </v-avatar>
              <v-avatar
                v-else-if="item.kansaiResult.prize === 'silver'"
                class="mx-2"
                color="grey"
              >
                <span class="white--text">銀賞</span>
              </v-avatar>
              <v-avatar
                v-else-if="item.kansaiResult.prize === 'bronze'"
                class="mx-2"
                color="brown"
              >
                <span class="white--text">銅賞</span>
              </v-avatar>
              <span v-else>不明</span>
            </v-card-text>
          </template>
        </v-card>
      </v-col>
    </v-row>
    <v-card class="hidden-xs-only pa-4">
      <v-card-title>
        <h2>吹奏楽コンクール</h2>
      </v-card-title>
      <v-simple-table>
        <template v-slot:default>
          <thead>
            <tr>
              <th class="text-left">西暦</th>
              <th class="text-left">指揮者</th>
              <th class="text-left">課題曲</th>
              <th class="text-left">自由曲</th>
              <th class="text-left">結果（県大会）</th>
              <th class="text-left">滋賀県代表</th>
              <th class="text-left">結果（関西大会）</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="item in competitionRecords" :key="item.year">
              <td>{{ item.year }}</td>
              <td>{{ item.conductor }}</td>
              <td>{{ item.required }}</td>
              <td>{{ item.free }}</td>
              <td>
                <v-avatar
                  v-if="item.prefResult.prize === 'gold'"
                  color="#BFA95F"
                  size="36"
                >
                  <span class="black--text">金賞</span>
                </v-avatar>
                <v-avatar
                  v-else-if="item.prefResult.prize === 'silver'"
                  color="grey"
                  size="36"
                >
                  <span class="white--text">銀賞</span>
                </v-avatar>
                <v-avatar
                  v-else-if="item.prefResult.prize === 'bronze'"
                  color="brown"
                  size="36"
                >
                  <span class="white--text">銅賞</span>
                </v-avatar>
                <span v-else>不明</span>
                <!-- <p v-if="item.prefResult.kiramekiPrize">きらめき</p> -->
              </td>
              <td v-if="item.prefResult.representative">○</td>
              <td v-else></td>
              <template v-if="item.prefResult.representative">
                <td>
                  <v-avatar
                    v-if="item.kansaiResult.prize === 'gold'"
                    color="#BFA95F"
                    size="36"
                  >
                    <span class="black--text">金賞</span>
                  </v-avatar>
                  <v-avatar
                    v-else-if="item.kansaiResult.prize === 'silver'"
                    color="grey"
                    size="36"
                  >
                    <span class="white--text">銀賞</span>
                  </v-avatar>
                  <v-avatar
                    v-else-if="item.kansaiResult.prize === 'bronze'"
                    color="brown"
                    size="36"
                  >
                    <span class="white--text">銅賞</span>
                  </v-avatar>
                  <span v-else>不明</span>
                </td>
              </template>
              <td v-else></td>
            </tr>
          </tbody>
        </template>
      </v-simple-table>
    </v-card>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      title: '大会記録',
      competitionRecords: require('~/assets/competitionRecords')
    }
  },
  head() {
    return {
      title: this.title
    }
  }
}
</script>
