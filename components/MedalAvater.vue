<template>
  <v-avatar v-if="prize === 'gold'" color="#BFA95F" size="36">
    <span class="black--text">金賞</span>
  </v-avatar>
  <v-avatar v-else-if="prize === 'silver'" color="grey" size="36">
    <span class="white--text">銀賞</span>
  </v-avatar>
  <v-avatar v-else-if="prize === 'bronze'" color="brown" size="36">
    <span class="white--text">銅賞</span>
  </v-avatar>
</template>

<script>
export default {
  props: {
    prize: {
      type: String,
      required: true
    }
  }
}
</script>
