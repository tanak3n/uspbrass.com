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
      <v-col v-for="item in competitionResults" :key="item.year" cols="12">
        <v-card>
          <v-card-title> {{ item.year }}年 </v-card-title>
          <v-card-text>
            <dl>
              <dt class="font-weight-bold">課題曲</dt>
              <dd class="ml-2">
                {{ item.required ? item.required : '不明' }}
              </dd>
              <dt class="font-weight-bold">自由曲</dt>
              <dd class="ml-2">
                {{ item.free ? item.free : '不明' }}
              </dd>
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
              color="yellow lighten-2"
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
                color="yellow lighten-2"
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
      <v-card-title><h2>吹奏楽コンクール</h2></v-card-title>
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
            <tr v-for="item in competitionResults" :key="item.year">
              <td>{{ item.year }}</td>
              <td>{{ item.conductor }}</td>
              <td>{{ item.required }}</td>
              <td>{{ item.free }}</td>
              <td>
                <v-avatar
                  v-if="item.prefResult.prize === 'gold'"
                  color="yellow lighten-2"
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
                    color="yellow lighten-2"
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
      competitionResults: [
        {
          year: '2019',
          required: 'IV 行進曲「道標の先に」／岡田 康汰',
          free: '森の贈り物／酒井 格',
          conductor: '橋本 周知',
          prefResult: {
            nth: '55',
            prize: 'gold',
            kiramekiPrize: false,
            representative: true
          },
          kansaiResult: {
            nth: '69',
            prize: 'bronze',
            representative: false
          }
        },
        {
          year: '2018',
          required: 'IV コンサート・マーチ「虹色の未来へ」／郷間 幹男',
          free: '交響的詩曲「走れメロス」／福島 弘和',
          conductor: '松浦 章仁',
          prefResult: {
            nth: '54',
            prize: 'gold',
            kiramekiPrize: true,
            representative: false
          }
        },
        {
          year: '2017',
          required: 'II マーチ・シャイニング・ロード／木内 涼',
          free: '想ひ麗し浄瑠璃姫の雫／樽屋 雅徳',
          conductor: '大西 祥生',
          prefResult: {
            nth: '53',
            prize: 'gold',
            kiramekiPrize: false,
            representative: true
          },
          kansaiResult: {
            nth: '67',
            prize: 'bronze',
            representative: false
          }
        },
        {
          year: '2016',
          required: 'I マーチ・スカイブルー・ドリーム／矢藤 学',
          free: '大いなる約束の大地～チンギス・ハーン／鈴木 英史',
          conductor: '大西 祥生',
          prefResult: {
            nth: '52',
            prize: 'silver',
            kiramekiPrize: false,
            representative: false
          }
        },
        {
          year: '2015',
          required: 'I 天空の旅 －吹奏楽のための譚詩－／石原 勇太郎',
          free: '梁塵秘抄〜熊野古道の幻想〜／福島 弘和',
          conductor: '大島 和香那',
          prefResult: {
            nth: '51',
            prize: 'silver',
            kiramekiPrize: false,
            representative: false
          }
        },
        {
          year: '2014',
          required: 'II 行進曲「勇気のトビラ」／高橋 宏樹',
          free: 'ドラゴンの山／S.ライニキー',
          conductor: '吉田 一基',
          prefResult: {
            nth: '50',
            prize: 'silver',
            kiramekiPrize: false,
            representative: false
          }
        },
        {
          year: '2013',
          required: 'IV エンターテインメント・マーチ／川北 栄樹',
          free: 'ノアの方舟／樽屋 雅徳',
          conductor: '平野 智子',
          prefResult: {
            nth: '49',
            prize: 'silver',
            kiramekiPrize: false,
            representative: false
          }
        },
        {
          year: '2012',
          required: 'II 行進曲「よろこびへ歩きだせ」／土井 康司',
          free: '吹奏楽のための音詩「輝きの海へ」／八木澤 教司',
          conductor: '倉田 智哉',
          prefResult: {
            nth: '48',
            prize: 'bronze',
            kiramekiPrize: false,
            representative: false
          }
        },
        {
          year: '2011',
          required: null,
          free: null,
          conductor: null,
          prefResult: {
            nth: '47',
            prize: 'silver',
            kiramekiPrize: true,
            representative: false
          }
        },
        {
          year: '2010',
          required: 'III 吹奏楽のための民謡「うちなーのてぃだ」／長野 雄行',
          free: 'ひとつの声に導かれる時／J.L.ホゼイ',
          conductor: '中村 美緒',
          prefResult: {
            nth: '46',
            prize: 'silver',
            kiramekiPrize: false,
            representative: false
          }
        },
        {
          year: '2009',
          required: 'IV マーチ「青空と太陽」／藤代 敏裕',
          free: '吹奏楽のための譚詩 天女の飛翔／八木澤 教司',
          conductor: '竹田 芙美',
          prefResult: {
            nth: '45',
            prize: 'silver',
            kiramekiPrize: false,
            representative: false
          }
        },
        {
          year: '2008',
          required: null,
          free: null,
          conductor: null,
          prefResult: {
            nth: '44',
            prize: 'silver',
            kiramekiPrize: true,
            representative: false
          }
        },
        {
          year: '2007',
          required: 'I ピッコロマーチ／田嶋 勉',
          free: 'シンフォニア・ノビリッシマ／R.ジェイガー',
          conductor: '前川 達郎',
          prefResult: {
            nth: '43',
            prize: 'silver',
            kiramekiPrize: false,
            representative: false
          }
        },
        {
          year: '2006',
          required: 'IV 海へ... 吹奏楽の為に／三澤 慶',
          free: '「モアイ」ー太陽を見つめる七体の巨像／八木澤 教司',
          conductor: '小坂 壮平',
          prefResult: {
            nth: '42',
            prize: 'gold',
            kiramekiPrize: false,
            representative: true
          },
          kansaiResult: {
            nth: '56',
            prize: 'bronze',
            representative: false
          }
        },
        {
          year: '2005',
          required: 'III ストリート・パフォーマーズ・マーチ／高橋宏樹',
          free: 'ヘイヴンダンス／D.R.ホルジンガー',
          conductor: '和田 浩平',
          prefResult: {
            nth: '41',
            prize: 'silver',
            kiramekiPrize: false,
            representative: false
          }
        },
        {
          year: '2004',
          required: 'I 吹奏楽のための「風之舞」／福田 洋介',
          free: 'ツイン・オークス／J.バーンズ',
          conductor: '石井 慎也',
          prefResult: {
            nth: '40',
            prize: 'silver',
            kiramekiPrize: false,
            representative: false
          }
        },
        {
          year: '2003',
          required: 'IV マーチ「ベストフレンド」／松浦 伸吾',
          free: 'オリエント急行／P.スパーク',
          conductor: '長野 光明',
          prefResult: {
            nth: '39',
            prize: 'silver',
            kiramekiPrize: false,
            representative: false
          }
        },
        {
          year: '2002',
          required: 'II ミニシンフォニー 変ホ長調／原 博',
          free: 'たなばた／酒井 格',
          conductor: '長野 光明',
          prefResult: {
            nth: '38',
            prize: 'silver',
            kiramekiPrize: false,
            representative: false
          }
        },
        {
          year: '2001',
          required: 'I 式典のための行進曲「栄光をたたえて」／内藤 淳一',
          free: '「プスタ」よりIII, IV／J.ヴァンデルロースト',
          conductor: '古株 洋',
          prefResult: {
            nth: '37',
            prize: 'silver',
            kiramekiPrize: false,
            representative: false
          }
        },
        {
          year: '2000',
          required: 'I 道祖神の詩／福島 弘和',
          free: '管楽器のための古典幻想曲／伊藤 康英',
          conductor: '古株 洋',
          prefResult: {
            nth: '36',
            prize: 'silver',
            kiramekiPrize: false,
            representative: false
          }
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
