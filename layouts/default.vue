<template>
  <div id="wrapper">
    <header>
      <img src="/logo.svg" />
    </header>
    <Nuxt />
  </div>
</template>
<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
    }
  }
}
</script>
<style scoped>
#wrapper{
  height: 100vh;
}
img {
  padding: 0.5em;
  display: block;
  width: 100%;
  text-align: center;
  width: 100%;
}
header {
  margin: 0 0.5em;
}
</style>
