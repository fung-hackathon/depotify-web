<template>
  <dev class="container">
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
  </dev>
</template>
<script>
export default {
  data: () => {
    return {
      emojis: [
        {
          emoji: '❤',
          state: false
        },
        {
          emoji: '😊',
          state: false
        },
        {
          emoji: '🥰',
          state: false
        },
        {
          emoji: '😋',
          state: false
        },
        {
          emoji: '🥳',
          state: false
        },
        {
          emoji: '💯',
          state: false
        }
      ],
      lock: false
    }
  },
  methods: {
    onButtonClicked (emoji) {
      this.lock = true
      emoji.state = true
      if (!this.lock) {
        // apiたたく
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
</style>
