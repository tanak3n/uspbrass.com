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
              <dd class="ml-2">{{ item.required || '不明' }}</dd>
              <dt class="font-weight-bold">自由曲</dt>
              <dd class="ml-2">{{ item.free || '不明' }}</dd>
              <dt class="font-weight-bold">指揮者</dt>
              <dd class="ml-2">
                {{ item.conductor || '不明' }}
              </dd>
            </dl>
          </v-card-text>
          <v-card-title>県大会</v-card-title>
          <v-card-text>
            <MedalAvater :prize="item.prefResult.prize" />
            <span v-if="item.prefResult.representative">滋賀県代表</span>
          </v-card-text>
          <template v-if="item.prefResult.representative">
            <v-card-title>関西大会</v-card-title>
            <v-card-text>
              <MedalAvater :prize="item.kansaiResult.prize" />
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
              <th class="text-left">年度</th>
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
              <td>{{ item.conductor || '不明' }}</td>
              <td>{{ item.required || '不明' }}</td>
              <td>{{ item.free || '不明' }}</td>
              <td>
                <MedalAvater :prize="item.prefResult.prize" />
              </td>
              <td>
                <span v-if="item.prefResult.representative">○</span>
              </td>
              <td>
                <MedalAvater
                  v-if="item.prefResult.representative"
                  :prize="item.kansaiResult.prize"
                />
              </td>
            </tr>
          </tbody>
        </template>
      </v-simple-table>
    </v-card>
    <h2 class="hidden-sm-and-up">アンサンブルコンテンスト</h2>
    <v-row class="hidden-sm-and-up">
      <v-col v-for="item in ensembleRecords" :key="item.year" cols="12">
        <v-card>
          <v-card-title>{{ item.year }}年</v-card-title>
          <v-card-text>
            <dl>
              <dt class="font-weight-bold">曲名</dt>
              <dd class="ml-2">{{ item.style }} {{ item.title || '不明' }}</dd>
            </dl>
          </v-card-text>
          <v-card-title>県大会</v-card-title>
          <v-card-text>
            <MedalAvater :prize="item.prefResult.prize" />
            <span v-if="item.prefResult.representative">滋賀県代表</span>
          </v-card-text>
          <template v-if="item.prefResult.representative">
            <v-card-title>関西大会</v-card-title>
            <v-card-text>
              <MedalAvater :prize="item.kansaiResult.prize" />
            </v-card-text>
          </template>
        </v-card>
      </v-col>
    </v-row>
    <v-card class="hidden-xs-only pa-4 mt-4">
      <v-card-title>
        <h2>アンサンブルコンテンスト</h2>
      </v-card-title>
      <v-simple-table>
        <template v-slot:default>
          <thead>
            <tr>
              <th class="text-left">年度</th>
              <th class="text-left">編成</th>
              <th class="text-left">曲名</th>
              <th class="text-left">結果（県大会）</th>
              <th class="text-left">滋賀県代表</th>
              <th class="text-left">結果（関西大会）</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="item in ensembleRecords" :key="item.year">
              <td>{{ item.year }}</td>
              <td>{{ item.style || '不明' }}</td>
              <td>{{ item.title || '不明' }}</td>
              <td>
                <MedalAvater :prize="item.prefResult.prize" />
              </td>
              <td>
                <span v-if="item.prefResult.representative">○</span>
              </td>
              <td>
                <MedalAvater
                  v-if="item.prefResult.representative"
                  :prize="item.kansaiResult.prize"
                />
              </td>
            </tr>
          </tbody>
        </template>
      </v-simple-table>
    </v-card>
  </v-container>
</template>

<script>
import MedalAvater from '~/components/MedalAvater'

export default {
  components: {
    MedalAvater
  },
  data() {
    return {
      title: '大会記録',
      competitionRecords: require('~/assets/competitionRecords'),
      ensembleRecords: require('~/assets/ensembleRecords')
    }
  },
  head() {
    return {
      title: this.title
    }
  }
}
</script>
