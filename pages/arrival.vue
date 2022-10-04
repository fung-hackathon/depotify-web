<template>
  <v-container fluid>
    <v-row>
      <div class="description">
        ご乗車ありがとうございました。<br>
        感謝を絵文字で伝えよう！
      </div>
    </v-row>
    <v-row>
      <ReactionButtons class="reaction" />
    </v-row>
    <v-row>
      <AdBox class="ad" />
    </v-row>
  </v-container>
</template>
<script>
import AdBox from '@/components/AdBox'
import ReactionButtons from '@/components/ReactionButtons'
export default {
  name: 'IndexPage',
  components: {
    AdBox,
    ReactionButtons
  }
}
</script>
<style scoped>
.description {
  font-size: 1.5em;
  padding:0 0.5em;
}
.ad {
  display: block;
  margin: auto;
}
</style>
