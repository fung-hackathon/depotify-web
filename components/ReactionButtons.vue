<template>
  <div>
    <p>
      {{ status }}
    </p>
    <p v-if="error != null">
      {{ error }}
    </p>
    <div class="container">
      <v-btn
        v-for="emoji in emojis"
        :key="emoji.emoji"
        :disabled="lock && !emoji.state"
        elevation="1"
        rounded
        x-large
        class="emoji"
        @click="onButtonClicked(emoji)"
      >
        {{ emoji.emoji }}
      </v-btn>
    </div>
  </div>
</template>
<script>
export default {
  data: () => {
    return {
      emojis: [
        {
          emoji: '❤',
          state: false,
          name: 'heart'
        },
        {
          emoji: '😊',
          state: false,
          name: 'blush'
        },
        {
          emoji: '🥰',
          state: false,
          name: 'smiling_face_with_3_hearts'
        },
        {
          emoji: '😋',
          state: false,
          name: 'yum'
        },
        {
          emoji: '🥳',
          state: false,
          name: 'partying_face'
        },
        {
          emoji: '💯',
          state: false,
          name: '100'
        }
      ],
      lock: false,
      status: '感謝を絵文字で伝えよう！',
      error: null
    }
  },
  methods: {
    onButtonClicked (emoji) {
      if (!this.lock) {
        // apiたたく
        this.$axios.post('/api/emotion', {
          userid: this.$route.query.userid,
          emotion: [emoji.name]
        }).then((res) => {
          this.status = '送信に成功しました'
          emoji.state = true
          this.lock = true
        }).catch((err) => {
          this.status = '送信に失敗しました'
          this.error = err
        })
      }
    }
  }
}
</script>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Noto+Color+Emoji&display=swap');
.emoji {
  font-family: 'Noto Color Emoji', sans-serif;
  font-size: 2em;
  width: 47%;
  margin: 2% 1.5%;
}
.container {
  display: flex;
  flex-wrap: wrap;
  margin: 0;
  padding: 1em 0;
}
p {
  font-size: 1.5em;
  padding:0 0.5em;
}
</style>
